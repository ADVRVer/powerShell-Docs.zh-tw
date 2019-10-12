---
ms.date: 06/12/2017
keywords: dsc,powershell,設定,安裝
title: DSCAutomationHostEnabled 登錄機碼
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954265"
---
><span data-ttu-id="cd7b8-103">適用於：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="cd7b8-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="cd7b8-104">DSCAutomationHostEnabled 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="cd7b8-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="cd7b8-105">DSC 使用 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** 下的 **DSCAutomationHostEnabled** 登錄機碼，在初始開機時啟用電腦的設定。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="cd7b8-106">**DSCAutomationHostEnabled** 支援三個模式：</span><span class="sxs-lookup"><span data-stu-id="cd7b8-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="cd7b8-107">DSCAutomationHostEnabled 值</span><span class="sxs-lookup"><span data-stu-id="cd7b8-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="cd7b8-108">描述</span><span class="sxs-lookup"><span data-stu-id="cd7b8-108">Description</span></span>   |
|---|---|
<span data-ttu-id="cd7b8-109">0</span><span class="sxs-lookup"><span data-stu-id="cd7b8-109">0</span></span> | <span data-ttu-id="cd7b8-110">不允許在開機時設定電腦。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="cd7b8-111">1</span><span class="sxs-lookup"><span data-stu-id="cd7b8-111">1</span></span> | <span data-ttu-id="cd7b8-112">允許在開機時設定電腦。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="cd7b8-113">2</span><span class="sxs-lookup"><span data-stu-id="cd7b8-113">2</span></span> | <span data-ttu-id="cd7b8-114">僅當 DSC 處於暫止或目前的狀態時，才允許設定電腦。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="cd7b8-115">這是預設值。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="cd7b8-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cd7b8-116">See Also</span></span>

<span data-ttu-id="cd7b8-117">如需如何使用此功能在初始機時執行設定的範例，請參閱[使用 DSC 在初始開機時設定虛擬機器](bootstrapDsc.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7b8-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>