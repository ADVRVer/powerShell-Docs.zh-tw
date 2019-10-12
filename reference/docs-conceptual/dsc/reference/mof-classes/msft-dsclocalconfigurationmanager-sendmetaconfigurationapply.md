---
ms.date: 06/12/2017
keywords: dsc,powershell,設定,安裝
title: SendMetaConfigurationApply 方法
ms.openlocfilehash: b2e420bafb8ea22aea43800f6e429d3ed785d1e8
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954875"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="1015c-103">SendMetaConfigurationApply 方法</span><span class="sxs-lookup"><span data-stu-id="1015c-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="1015c-104">設定用於控制設定代理程式的本機設定管理員設定。</span><span class="sxs-lookup"><span data-stu-id="1015c-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="1015c-105">語法</span><span class="sxs-lookup"><span data-stu-id="1015c-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="1015c-106">參數</span><span class="sxs-lookup"><span data-stu-id="1015c-106">Parameters</span></span>

<span data-ttu-id="1015c-107">*ConfigurationData* \[in\] 設定的環境資料。</span><span class="sxs-lookup"><span data-stu-id="1015c-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="1015c-108">*force* \[in\] **true** 表示強制停止該設定。</span><span class="sxs-lookup"><span data-stu-id="1015c-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="1015c-109">傳回值</span><span class="sxs-lookup"><span data-stu-id="1015c-109">Return value</span></span>

<span data-ttu-id="1015c-110">若成功即傳回零；否則傳回錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="1015c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1015c-111">備註</span><span class="sxs-lookup"><span data-stu-id="1015c-111">Remarks</span></span>

<span data-ttu-id="1015c-112">此為靜態方法。</span><span class="sxs-lookup"><span data-stu-id="1015c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1015c-113">需求</span><span class="sxs-lookup"><span data-stu-id="1015c-113">Requirements</span></span>

<span data-ttu-id="1015c-114">**MOF**：DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1015c-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1015c-115">**命名空間**：Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1015c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1015c-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1015c-116">See also</span></span>

[<span data-ttu-id="1015c-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1015c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)