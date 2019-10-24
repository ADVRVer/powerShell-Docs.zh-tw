---
title: GetProc01 （C#）範例程式碼 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65094bb7-1972-44b3-b8b0-5f639860b58c
caps.latest.revision: 5
ms.openlocfilehash: 06a24266eb8fda6e4f138f1f77ae702f7454e525
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366797"
---
# <a name="getproc01-c-sample-code"></a>GetProc01 (C#) 程式碼範例

下列程式碼顯示 GetProc01 範例 Cmdlet 的執行。 請注意，藉由將處理常式抓取的實際工作保留到[system.diagnostics.process.getprocesses *](/dotnet/api/System.Diagnostics.Process.GetProcesses)方法，即可簡化此 Cmdlet。

> [!NOTE]
> 您可以使用適用C#于 Windows Vista 和 .NET Framework 3.0 執行時間元件的 Microsoft Windows 軟體發展工具組，下載這個 getproc01.cs 的原始程式檔（）。 如需下載指示，請參閱[如何安裝 Windows powershell 和下載 Windows POWERSHELL SDK](/powershell/developer/installing-the-windows-powershell-sdk)。
>
> 下載的來源檔案可在 **@no__t 1PowerShell 範例 >** 目錄中取得。

## <a name="code-sample"></a>程式碼範例

[!code-csharp[GetProcessSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample01/GetProcessSample01.cs#L11-L126 "GetProcessSample01.cs")]

## <a name="see-also"></a>另請參閱

[Windows PowerShell 程式設計人員指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)