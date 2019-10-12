---
ms.date: 09/20/2019
keywords: dsc,powershell,設定,安裝
title: DSC WaitForAny 資源
ms.openlocfilehash: 61fee456d2652e08ed9bdbe64457627ff5b2e145
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952995"
---
# <a name="dsc-waitforany-resource"></a><span data-ttu-id="03e21-103">DSC WaitForAny 資源</span><span class="sxs-lookup"><span data-stu-id="03e21-103">DSC WaitForAny Resource</span></span>

> <span data-ttu-id="03e21-104">適用於：Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="03e21-104">Applies To: Windows PowerShell 5.1</span></span>

<span data-ttu-id="03e21-105">您可以在 [DSC 設定](../../../configurations/configurations.md)中的節點區塊內使用 **WaitForAny**「預期狀態設定」(DSC) 資源，以指定與其他節點上之設定的相依性。</span><span class="sxs-lookup"><span data-stu-id="03e21-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="03e21-106">如果 **ResourceName** 屬性所指定的資源在 **NodeName** 屬性所定義的任何目標節點上處於預期狀態，此資源即可視為成功。</span><span class="sxs-lookup"><span data-stu-id="03e21-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on any target nodes defined in the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="03e21-107">**WaitForAny** 資源使用 Windows 遠端管理來檢查其他節點的狀態。</span><span class="sxs-lookup"><span data-stu-id="03e21-107">**WaitForAny** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="03e21-108">如需 WinRM 連接埠和安全性需求的詳細資訊，請參閱 [PowerShell 遠端安全性考量](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6)。</span><span class="sxs-lookup"><span data-stu-id="03e21-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="03e21-109">語法</span><span class="sxs-lookup"><span data-stu-id="03e21-109">Syntax</span></span>

```Syntax
WaitForAny [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="03e21-110">Properties</span><span class="sxs-lookup"><span data-stu-id="03e21-110">Properties</span></span>

|<span data-ttu-id="03e21-111">屬性</span><span class="sxs-lookup"><span data-stu-id="03e21-111">Property</span></span> |<span data-ttu-id="03e21-112">描述</span><span class="sxs-lookup"><span data-stu-id="03e21-112">Description</span></span> |
|---|---|
|<span data-ttu-id="03e21-113">ResourceName</span><span class="sxs-lookup"><span data-stu-id="03e21-113">ResourceName</span></span> |<span data-ttu-id="03e21-114">所要依據的資源名稱。</span><span class="sxs-lookup"><span data-stu-id="03e21-114">The resource name to depend on.</span></span> <span data-ttu-id="03e21-115">如果此資源屬於不同的設定，請將名稱格式化為 `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`。</span><span class="sxs-lookup"><span data-stu-id="03e21-115">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="03e21-116">NodeName</span><span class="sxs-lookup"><span data-stu-id="03e21-116">NodeName</span></span> |<span data-ttu-id="03e21-117">所要依據之資源的目標節點。</span><span class="sxs-lookup"><span data-stu-id="03e21-117">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="03e21-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="03e21-118">RetryIntervalSec</span></span> |<span data-ttu-id="03e21-119">進行重試之前的秒數。</span><span class="sxs-lookup"><span data-stu-id="03e21-119">The number of seconds before retrying.</span></span> <span data-ttu-id="03e21-120">最小值為 1。</span><span class="sxs-lookup"><span data-stu-id="03e21-120">Minimum is 1.</span></span> |
|<span data-ttu-id="03e21-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="03e21-121">RetryCount</span></span> |<span data-ttu-id="03e21-122">重試次數上限。</span><span class="sxs-lookup"><span data-stu-id="03e21-122">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="03e21-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="03e21-123">ThrottleLimit</span></span> |<span data-ttu-id="03e21-124">可同時連線的電腦數目。</span><span class="sxs-lookup"><span data-stu-id="03e21-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="03e21-125">預設值為 `New-CimSession` 預設值。</span><span class="sxs-lookup"><span data-stu-id="03e21-125">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="03e21-126">通用屬性</span><span class="sxs-lookup"><span data-stu-id="03e21-126">Common properties</span></span>

|<span data-ttu-id="03e21-127">屬性</span><span class="sxs-lookup"><span data-stu-id="03e21-127">Property</span></span> |<span data-ttu-id="03e21-128">描述</span><span class="sxs-lookup"><span data-stu-id="03e21-128">Description</span></span> |
|---|---|
|<span data-ttu-id="03e21-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="03e21-129">DependsOn</span></span> |<span data-ttu-id="03e21-130">表示必須先執行另一個資源的設定，再設定這個資源。</span><span class="sxs-lookup"><span data-stu-id="03e21-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="03e21-131">例如，如果第一個想要執行的資源設定指令碼區塊識別碼是 ResourceName，而其類型是 ResourceType，則使用這個屬性的語法就是 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="03e21-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="03e21-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="03e21-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="03e21-133">設定用於執行整個資源的認證。</span><span class="sxs-lookup"><span data-stu-id="03e21-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="03e21-134">已在 WMF 5.0 中新增 **PsDscRunAsCredential** 通用屬性，以允許在其他認證的內容中執行任何 DSC 資源。</span><span class="sxs-lookup"><span data-stu-id="03e21-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="03e21-135">如需詳細資訊，請參閱[搭配 DSC 資源使用認證](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="03e21-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="03e21-136">範例</span><span class="sxs-lookup"><span data-stu-id="03e21-136">Example</span></span>

<span data-ttu-id="03e21-137">如需有關如何使用此資源的範例，請參閱[指定跨節點相依性](../../../configurations/crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="03e21-137">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>