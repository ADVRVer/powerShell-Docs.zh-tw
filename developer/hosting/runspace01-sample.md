---
title: Runspace01 範例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c1c59c-6da5-4cda-9562-e8059177fee1
caps.latest.revision: 11
ms.openlocfilehash: eec9c616fc6d5240db185f764a3ea2c8f9575d03
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057904"
---
# <a name="runspace01-sample"></a><span data-ttu-id="1caf3-102">Runspace01 範例</span><span class="sxs-lookup"><span data-stu-id="1caf3-102">Runspace01 Sample</span></span>

<span data-ttu-id="1caf3-103">此範例示範如何使用[System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)類別來執行[Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet 以同步方式。</span><span class="sxs-lookup"><span data-stu-id="1caf3-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span> <span data-ttu-id="1caf3-104">[Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet 會傳回[System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)本機電腦上執行每個處理序的物件。</span><span class="sxs-lookup"><span data-stu-id="1caf3-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer.</span></span> <span data-ttu-id="1caf3-105">值[System.Diagnostics.Process.Processname\*](/dotnet/api/System.Diagnostics.Process.ProcessName)並[System.Diagnostics.Process.Handlecount\*](/dotnet/api/System.Diagnostics.Process.Handlecount)屬性然後從傳回的物件中擷取並顯示在主控台中視窗。</span><span class="sxs-lookup"><span data-stu-id="1caf3-105">The values of the [System.Diagnostics.Process.Processname\*](/dotnet/api/System.Diagnostics.Process.ProcessName) and [System.Diagnostics.Process.Handlecount\*](/dotnet/api/System.Diagnostics.Process.Handlecount) properties are then extracted from the returned objects and displayed in a console window.</span></span>

## <a name="requirements"></a><span data-ttu-id="1caf3-106">需求</span><span class="sxs-lookup"><span data-stu-id="1caf3-106">Requirements</span></span>

 <span data-ttu-id="1caf3-107">這個範例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="1caf3-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1caf3-108">示範</span><span class="sxs-lookup"><span data-stu-id="1caf3-108">Demonstrates</span></span>

- <span data-ttu-id="1caf3-109">建立[System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)執行命令的物件。</span><span class="sxs-lookup"><span data-stu-id="1caf3-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run a command.</span></span>

- <span data-ttu-id="1caf3-110">將命令加入至的管線[System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)物件。</span><span class="sxs-lookup"><span data-stu-id="1caf3-110">Adding a command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="1caf3-111">以同步方式執行命令。</span><span class="sxs-lookup"><span data-stu-id="1caf3-111">Running the command synchronously.</span></span>

- <span data-ttu-id="1caf3-112">使用[System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject)命令所傳回的物件中擷取屬性的物件。</span><span class="sxs-lookup"><span data-stu-id="1caf3-112">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract properties from the objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="1caf3-113">範例</span><span class="sxs-lookup"><span data-stu-id="1caf3-113">Example</span></span>

 <span data-ttu-id="1caf3-114">此範例會執行[Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)指令程式以同步方式在 Windows PowerShell 所提供的預設 runspace。</span><span class="sxs-lookup"><span data-stu-id="1caf3-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously in the default runspace provided by Windows PowerShell.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="1caf3-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1caf3-115">See Also</span></span>