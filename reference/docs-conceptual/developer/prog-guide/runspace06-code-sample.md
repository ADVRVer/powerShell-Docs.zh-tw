---
title: RunSpace06 程式碼範例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: f0197e6ca3535b72f843ba52e97381c0f2531598
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366487"
---
# <a name="runspace06-code-sample"></a>RunSpace06 程式碼範例

以下是[使用 Windows PowerShell 嵌入式管理單元設定運行](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83)時間中所述之 Runspace06 範例的原始程式碼。 這個範例應用程式會根據 Windows PowerShell 嵌入式管理單元建立執行時間，然後使用單一命令來執行管線。 若要這樣做，應用程式會建立運行時設定資訊、建立運行空間、使用單一命令建立管線，然後執行管線。

> [!NOTE]
> 您可以使用適用C#于 windows Vista 和 Microsoft .NET Framework 3.0 執行時間元件的 Windows 軟體發展工具組，下載原始程式檔（runspace06.cs）。 如需下載指示，請參閱[如何安裝 Windows powershell 和下載 Windows POWERSHELL SDK](/powershell/developer/installing-the-windows-powershell-sdk)。
>
> 下載的來源檔案可在 **@no__t 1PowerShell 範例 >** 目錄中取得。

## <a name="code-sample"></a>程式碼範例

[!code-csharp[Runspace06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a>另請參閱

[Windows PowerShell 程式設計人員指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)