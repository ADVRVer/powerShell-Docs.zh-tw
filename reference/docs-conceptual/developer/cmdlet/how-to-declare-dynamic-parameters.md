---
title: 如何宣告動態參數 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: a9c530cdc66302eb6b3d9d2b284eeb486c3b2ba9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364417"
---
# <a name="how-to-declare-dynamic-parameters"></a>如何宣告動態參數

這個範例示範如何定義在執行時間新增至 Cmdlet 的動態參數。 在此範例中，每當使用者指定 `Employee` 切換參數時，就會將 `Department` 參數新增至 Cmdlet。 如需動態參數的詳細資訊，請參閱[Cmdlet 動態參數](./cmdlet-dynamic-parameters.md)。

## <a name="to-define-dynamic-parameters"></a>若要定義動態參數

1. 在 Cmdlet 類別宣告中，新增[Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)介面，如下所示。

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. 呼叫[Idynamicparameters. Getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)方法，它會傳回已定義動態參數的物件。 在此範例中，當指定 `Employee` 參數時，會呼叫方法。

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. 宣告定義要加入之動態參數的類別。 您可以使用您用來宣告靜態 Cmdlet 參數的屬性，以宣告動態參數。

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a>範例

在此範例中，每當使用者指定 `Employee` 參數時，就會新增 `Department` 參數。 @No__t-0 參數是選擇性參數，而 ValidateSet 屬性則是用來指定允許的引數。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a>另請參閱

[Runtimedefinedparameterdictionary。](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[Idynamicparameters. Getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Cmdlet 動態參數](./cmdlet-dynamic-parameters.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)