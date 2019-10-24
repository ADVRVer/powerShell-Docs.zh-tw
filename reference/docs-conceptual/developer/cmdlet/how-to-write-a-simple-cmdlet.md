---
title: 如何撰寫簡單的 Cmdlet |Microsoft Docs
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365467"
---
# <a name="how-to-write-a-cmdlet"></a>如何撰寫 Cmdlet

本文說明如何撰寫 Cmdlet。 @No__t-0 Cmdlet 會使用單一使用者名稱做為輸入，然後將問候語寫入該使用者。 雖然此 Cmdlet 不會執行太多工作，但此範例會示範 Cmdlet 的主要區段。

## <a name="steps-to-write-a-cmdlet"></a>撰寫 Cmdlet 的步驟

1. 若要將類別宣告為 Cmdlet，請使用**Cmdlet**屬性。 **Cmdlet**屬性會指定 Cmdlet 名稱的動詞和名詞。

   如需**Cmdlet**屬性的詳細資訊，請參閱[CmdletAttribute](cmdlet-attribute-declaration.md)宣告。

2. 指定類別的名稱。

3. 指定 Cmdlet 衍生自下列其中一個類別：

   * [[系統管理]。 Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)
   * [PSCmdlet。](/dotnet/api/System.Management.Automation.PSCmdlet)

4. 若要定義 Cmdlet 的參數，請使用**參數**屬性。 在此情況下，只會指定一個必要的參數。

   如需**參數**屬性的詳細資訊，請參閱[ParameterAttribute](parameter-attribute-declaration.md)宣告。

5. 覆寫處理輸入的輸入處理方法。 在此情況下，會覆寫[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法。

6. 若要寫入問候語，請使用[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)方法。
   此問候語會以下列格式顯示：

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a>範例

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>另請參閱

[[系統管理]。 Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)

[PSCmdlet。](/dotnet/api/System.Management.Automation.PSCmdlet)

[ProcessRecord 的管理元件](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[WriteObject 的管理元件](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[CmdletAttribute 宣告](cmdlet-attribute-declaration.md)

[ParameterAttribute 宣告](parameter-attribute-declaration.md)

[撰寫 Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md)