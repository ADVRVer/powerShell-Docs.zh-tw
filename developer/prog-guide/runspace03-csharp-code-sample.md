---
title: RunSpace03 (C#) 程式碼範例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 0e80f4d850a7c6dc044526a56b92f16eea4040b5
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429902"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="068ea-102">RunSpace03 (C#) 程式碼範例</span><span class="sxs-lookup"><span data-stu-id="068ea-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="068ea-103">以下是C#中所述的主控台應用程式的原始程式碼[建立主控台應用程式，執行指定指令碼](http://msdn.microsoft.com/en-us/a93e6006-36db-4bcc-b9da-c5bebf4ffd68)。</span><span class="sxs-lookup"><span data-stu-id="068ea-103">Here is the C# source code for the console application described in [Creating a Console Application That Runs a Specified Script](http://msdn.microsoft.com/en-us/a93e6006-36db-4bcc-b9da-c5bebf4ffd68).</span></span> <span data-ttu-id="068ea-104">這個範例會使用[System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)類別來執行的指令碼，擷取處理資訊，請使用傳遞至指令碼的程序名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="068ea-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="068ea-105">它會顯示如何將輸入的物件傳遞至指令碼以及如何擷取錯誤物件，以及輸出物件。</span><span class="sxs-lookup"><span data-stu-id="068ea-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="068ea-106">您可以下載C#此範例使用的 Microsoft Windows 軟體開發套件的 Windows Vista 和 Microsoft.NET Framework 3.0 執行階段元件的原始程式檔 (runspace03.cs)。</span><span class="sxs-lookup"><span data-stu-id="068ea-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="068ea-107">如需下載指示，請參閱[如何安裝 Windows PowerShell 並下載 Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="068ea-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="068ea-108">已下載的原始程式檔位於 **\<PowerShell 範例 >** 目錄。</span><span class="sxs-lookup"><span data-stu-id="068ea-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="068ea-109">程式碼範例</span><span class="sxs-lookup"><span data-stu-id="068ea-109">Code Sample</span></span>

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a><span data-ttu-id="068ea-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="068ea-110">See Also</span></span>

[<span data-ttu-id="068ea-111">Windows PowerShell 程式設計人員指南</span><span class="sxs-lookup"><span data-stu-id="068ea-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="068ea-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="068ea-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)