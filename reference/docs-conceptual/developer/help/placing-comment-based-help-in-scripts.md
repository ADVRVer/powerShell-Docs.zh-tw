---
title: 將註解型說明置於指令碼
ms.date: 09/12/2016
ms.openlocfilehash: a3ade6c3138826b924939056b9d1ffb233006d44
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893181"
---
# <a name="placing-comment-based-help-in-scripts"></a>將註解型說明置於指令碼

本主題說明如何為腳本放置以批註為基礎的說明，讓 `Get-Help` Cmdlet 將批註式說明主題與腳本建立關聯，而不是腳本中任何可能的功能。

## <a name="where-to-place-comment-based-help-for-a-script"></a>在何處放置腳本的批註型說明

- 在指令檔的開頭。

  腳本說明只能透過批註和空白行放在腳本的前面。

- 在指令檔的結尾。

  如果腳本主體中的第一個專案（在說明後面）是函式宣告，腳本說明結尾和函式宣告之間必須至少有兩行空白行。 否則，說明會被解釋為函數的說明，而不是腳本的說明。

## <a name="examples-of-help-placement-in-a-script"></a>腳本中的說明位置範例

下列範例會顯示腳本的批註式說明的每個放置選項。

### <a name="help-at-the-beginning-of-a-script"></a>腳本開頭的說明

下列範例會顯示以批註為基礎的腳本開頭。

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a>腳本結尾的說明

 下列範例會顯示以批註為基礎的腳本結尾。

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
