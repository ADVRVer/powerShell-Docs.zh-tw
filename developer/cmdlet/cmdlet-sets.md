---
title: 指令程式設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcf0739e-920e-4dd8-afca-2c6d6927bc2a
caps.latest.revision: 10
ms.openlocfilehash: ef3b5bab5dcafc578397bcb4f071776bbdeaced1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058261"
---
# <a name="cmdlet-sets"></a><span data-ttu-id="5dd34-102">Cmdlet 集合</span><span class="sxs-lookup"><span data-stu-id="5dd34-102">Cmdlet Sets</span></span>

<span data-ttu-id="5dd34-103">當您設計您的 cmdlet 時，您可能會遇到您要在相同的資料上執行數個動作的情況。</span><span class="sxs-lookup"><span data-stu-id="5dd34-103">When you design your cmdlets, you might encounter cases in which you need to perform several actions on the same piece of data.</span></span> <span data-ttu-id="5dd34-104">例如，您可能需要取得和設定資料或啟動和停止處理程序。</span><span class="sxs-lookup"><span data-stu-id="5dd34-104">For example, you might need to get and set data or start and stop a process.</span></span> <span data-ttu-id="5dd34-105">但是您必須建立個別的 cmdlet，來執行每個動作，您 cmdlet 的設計應該包含之個別 cmdlet 的類別均衍生自此基底類別。</span><span class="sxs-lookup"><span data-stu-id="5dd34-105">Although you will need to create separate cmdlets to perform each action, your cmdlet design should include a base class from which the classes for the individual cmdlets are derived.</span></span>

<span data-ttu-id="5dd34-106">實作的基底類別時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="5dd34-106">Keep the following things in mind when implementing a base class.</span></span>

- <span data-ttu-id="5dd34-107">宣告基底類別中，所有衍生的 cmdlet 所使用的任何一般參數。</span><span class="sxs-lookup"><span data-stu-id="5dd34-107">Declare any common parameters used by all the derived cmdlets in the base class.</span></span>

- <span data-ttu-id="5dd34-108">將特定 cmdlet 的參數加入適當的指令程式類別。</span><span class="sxs-lookup"><span data-stu-id="5dd34-108">Add cmdlet-specific parameters to the appropriate cmdlet class.</span></span>

- <span data-ttu-id="5dd34-109">覆寫適當的輸入處理方法的基底類別。</span><span class="sxs-lookup"><span data-stu-id="5dd34-109">Override the appropriate input processing method in the base class.</span></span>

- <span data-ttu-id="5dd34-110">宣告[System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute)屬性上的所有 cmdlet 類別，但未宣告它的基底類別。</span><span class="sxs-lookup"><span data-stu-id="5dd34-110">Declare the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute on all cmdlet classes, but do not declare it on the base class.</span></span>

- <span data-ttu-id="5dd34-111">實作[System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)或是[System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)類別的名稱和描述會反映出一組 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5dd34-111">Implement a [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class whose name and description reflects the set of cmdlets.</span></span>

## <a name="example"></a><span data-ttu-id="5dd34-112">範例</span><span class="sxs-lookup"><span data-stu-id="5dd34-112">Example</span></span>

<span data-ttu-id="5dd34-113">下列範例顯示取得跨處理序使用的基底類別和衍生自相同基底類別的停止程序 cmdlet 的實作。</span><span class="sxs-lookup"><span data-stu-id="5dd34-113">The following example shows the implementation of a base class that is used by Get-Proc and Stop-Proc cmdlet that derive from the same base class.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;             //Windows PowerShell namespace.

namespace Microsoft.Samples.PowerShell.Commands
{

  #region ProcessCommands

  /// <summary>
  /// This class implements a Stop-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>
  [Cmdlet(VerbsLifecycle.Stop, "Proc", SupportsShouldProcess = true)]
  public class StopProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      if (ShouldProcess(process.ProcessName, "Stop-Proc"))
      {
        process.Kill();
      }
    }
  }

  /// <summary>
  /// This class implements a Get-Proc cmdlet. The parameters
  /// for this cmdlet are defined by the BaseProcCommand class.
  /// </summary>

  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : BaseProcCommand
  {
    public override void ProcessObject(Process process)
    {
      WriteObject(process);
    }
  }

  /// <summary>
  /// This class is the base class that defines the common
  /// functionality used by the Get-Proc and Stop-Proc
  /// cmdlets.
  /// </summary>
  public class BaseProcCommand : Cmdlet
  {
    #region Parameters

    // Defines the Name parameter that is used to
    // specify a process by its name.
    [Parameter(
               Position = 0,
               Mandatory = true,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true
    )]
    public string[] Name
    {
      get { return processNames; }
      set { processNames = value; }
    }
    private string[] processNames;

    // Defines the Exclude parameter that is used to
    // specify which processes should be excluded when
    // the cmdlet performs its action.
    [Parameter()]
    public string[] Exclude
    {
      get { return excludeNames; }
      set { excludeNames = value; }
    }
    private string[] excludeNames = new string[0];
    #endregion Parameters

    public virtual void ProcessObject(Process process)
    {
      throw new NotImplementedException("This method should be overridden.");
    }

    #region Cmdlet Overrides
    // <summary>
    // For each of the requested process names, retrieve and write
    // the associated processes.
    // </summary>
    protected override void ProcessRecord()
    {
      // Set up the wildcard characters used in resolving
      // the process names.
      WildcardOptions options = WildcardOptions.IgnoreCase |
                                WildcardOptions.Compiled;

      WildcardPattern[] include = new WildcardPattern[Name.Length];
      for (int i = 0; i < Name.Length; i++)
      {
        include[i] = new WildcardPattern(Name[i], options);
      }

      WildcardPattern[] exclude = new WildcardPattern[Exclude.Length];
      for (int i = 0; i < Exclude.Length; i++)
      {
        exclude[i] = new WildcardPattern(Exclude[i], options);
      }

      foreach (Process p in Process.GetProcesses())
      {
        foreach (WildcardPattern wIn in include)
        {
          if (wIn.IsMatch(p.ProcessName))
          {
            bool processThisOne = true;
            foreach (WildcardPattern wOut in exclude)
            {
              if (wOut.IsMatch(p.ProcessName))
              {
                processThisOne = false;
                break;
              }
            }
            if (processThisOne)
            {
              ProcessObject(p);
            }
            break;
          }
        }
      }
    }
    #endregion Cmdlet Overrides
  }
    #endregion ProcessCommands
}
```

## <a name="see-also"></a><span data-ttu-id="5dd34-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5dd34-114">See Also</span></span>

[<span data-ttu-id="5dd34-115">撰寫 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5dd34-115">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)