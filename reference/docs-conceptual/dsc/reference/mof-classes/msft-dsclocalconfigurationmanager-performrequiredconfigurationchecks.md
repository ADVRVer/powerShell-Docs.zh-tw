---
ms.date: 06/12/2017
keywords: dsc,powershell,設定,安裝
title: PerformRequiredConfigurationChecks 方法
ms.openlocfilehash: 909e3a48d08e0220ab0efc6a03bea7ead5d9843e
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "71955005"
---
# <a name="performrequiredconfigurationchecks-method"></a>PerformRequiredConfigurationChecks 方法

使用工作排程器開始一致性檢查。

## <a name="syntax"></a>語法

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>參數

*Flags* \[in\] 位元遮罩，指定要執行的一致性檢查類型。 下列值有效，且可以透過位元 **OR** 運算進行結合︰

|值 |描述 |
|:--- |:---|
|**1** | 標準的一致性檢查。 |
|**2** | 重新開機後持續的一致性檢查。 此值不應與其他值結合。 |
|**4** | 應從節點中繼設定中所指定的提取伺服器，提取設定。 此值應一律使用 **5** 的值和 **1** 結合。 |
|**8** | 將狀態傳送到報表伺服器。 |

## <a name="return-value"></a>傳回值

若成功即傳回零；否則傳回錯誤碼。

## <a name="remarks"></a>備註

此為靜態方法。

## <a name="requirements"></a>需求

**MOF**：DscCore.mof

**命名空間**：Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>另請參閱

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
