---
ms.date: 05/22/2020
keywords: powershell,cmdlet
title: 如何使用 PowerShell 文件
ms.openlocfilehash: 259eb1eea1dc7e8b5ae5730f97c938b838a320bf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808260"
---
# <a name="how-to-use-the-powershell-documentation"></a>如何使用 PowerShell 文件

歡迎使用 PowerShell 線上文件。 此網站包含適用於下列 PowerShell 版本的 Cmdlet 參考：

- PowerShell 7
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>尋找文章並選取版本

有兩種方式可搜尋文件中的內容。最簡單方式是使用版本選擇器下方的 [篩選] 方塊。 只要輸入出現在文章標題中的字組即可。 此頁面會顯示相符的文章清單。 您也可以選取從該清單中搜尋整個網站的選項。

根據預設，此網站會顯示最新發行版本的 PowerShell 文件。 某些 Cmdlet 在各種 PowerShell 版本中的運作方式不同。 請確定您檢視您所使用 PowerShell 版本的文件。

使用頁面頂端的版本選擇器，選取您想要的 PowerShell 版本。

![版本選擇器](media/how-to-use-docs/version-search.gif)

您可以透過檢查 `$PSversionTable.PSVersion` 值來檢查您使用的 PowerShell 版本。 下列範例顯示 Windows PowerShell v5.1 的輸出。

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="finding-articles-for-previous-versions"></a>尋找舊版文章

舊版 PowerShell 的文件已封存在我們的[舊版](https://aka.ms/PSLegacyDocs)網站中。

此網站包含下列主題的文件：

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- PowerShell 工作流程
- PowerShell Web 存取
