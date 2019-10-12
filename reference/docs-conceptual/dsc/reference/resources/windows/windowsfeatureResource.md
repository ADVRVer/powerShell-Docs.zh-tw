---
ms.date: 09/20/2019
keywords: dsc,powershell,設定,安裝
title: DSC WindowsFeature 資源
ms.openlocfilehash: d3384b1f45324df6b6b209f25b64d9d77615ad7f
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954625"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="4246f-103">DSC WindowsFeature 資源</span><span class="sxs-lookup"><span data-stu-id="4246f-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="4246f-104">適用於：Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="4246f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="4246f-105">Windows PowerShell 預期狀態設定 (DSC) 的 **WindowsFeature** 資源提供一個機制，確保可在目標節點上新增或移除角色和功能。</span><span class="sxs-lookup"><span data-stu-id="4246f-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="4246f-106">語法</span><span class="sxs-lookup"><span data-stu-id="4246f-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ Source = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="4246f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="4246f-107">Properties</span></span>

|<span data-ttu-id="4246f-108">屬性</span><span class="sxs-lookup"><span data-stu-id="4246f-108">Property</span></span> |<span data-ttu-id="4246f-109">描述</span><span class="sxs-lookup"><span data-stu-id="4246f-109">Description</span></span> |
|---|---|
|<span data-ttu-id="4246f-110">名稱</span><span class="sxs-lookup"><span data-stu-id="4246f-110">Name</span></span> |<span data-ttu-id="4246f-111">表示您想要確保新增或移除的角色或功能名稱。</span><span class="sxs-lookup"><span data-stu-id="4246f-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="4246f-112">這與來自 [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) Cmdlet 的 **Name** 屬性相同，不是角色或功能的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="4246f-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="4246f-113">認證</span><span class="sxs-lookup"><span data-stu-id="4246f-113">Credential</span></span> |<span data-ttu-id="4246f-114">表示要用以新增或移除角色或功能的認證。</span><span class="sxs-lookup"><span data-stu-id="4246f-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="4246f-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="4246f-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="4246f-116">將此屬性設定為 `$true` 可讓您使用以 **Name** 屬性指定的功能狀態，來確保所有必要子功能的狀態。</span><span class="sxs-lookup"><span data-stu-id="4246f-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="4246f-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="4246f-117">LogPath</span></span> |<span data-ttu-id="4246f-118">表示要讓資源提供者記錄作業的記錄檔路徑。</span><span class="sxs-lookup"><span data-stu-id="4246f-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |
|<span data-ttu-id="4246f-119">來源</span><span class="sxs-lookup"><span data-stu-id="4246f-119">Source</span></span> |<span data-ttu-id="4246f-120">如有必要，表示用於安裝的來源檔案位置。</span><span class="sxs-lookup"><span data-stu-id="4246f-120">Indicates the location of the source file to use for installation, if necessary.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4246f-121">通用屬性</span><span class="sxs-lookup"><span data-stu-id="4246f-121">Common properties</span></span>

|<span data-ttu-id="4246f-122">屬性</span><span class="sxs-lookup"><span data-stu-id="4246f-122">Property</span></span> |<span data-ttu-id="4246f-123">描述</span><span class="sxs-lookup"><span data-stu-id="4246f-123">Description</span></span> |
|---|---|
|<span data-ttu-id="4246f-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4246f-124">DependsOn</span></span> |<span data-ttu-id="4246f-125">表示必須先執行另一個資源的設定，再設定這個資源。</span><span class="sxs-lookup"><span data-stu-id="4246f-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4246f-126">例如，如果第一個想要執行的資源設定指令碼區塊識別碼是 ResourceName，而其類型是 ResourceType，則使用這個屬性的語法就是 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="4246f-126">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="4246f-127">Ensure</span><span class="sxs-lookup"><span data-stu-id="4246f-127">Ensure</span></span> |<span data-ttu-id="4246f-128">表示角色或功能是否新增。</span><span class="sxs-lookup"><span data-stu-id="4246f-128">Indicates if the role or feature is added.</span></span> <span data-ttu-id="4246f-129">若要確保新增角色或功能，請將此屬性設定為 **Present**。</span><span class="sxs-lookup"><span data-stu-id="4246f-129">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="4246f-130">若要確保移除角色或功能，請將此屬性設定為 **Absent**。</span><span class="sxs-lookup"><span data-stu-id="4246f-130">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="4246f-131">預設值為 **Present**。</span><span class="sxs-lookup"><span data-stu-id="4246f-131">The default value is **Present**.</span></span> |
|<span data-ttu-id="4246f-132">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="4246f-132">PsDscRunAsCredential</span></span> |<span data-ttu-id="4246f-133">設定用於執行整個資源的認證。</span><span class="sxs-lookup"><span data-stu-id="4246f-133">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="4246f-134">已在 WMF 5.0 中新增 **PsDscRunAsCredential** 通用屬性，以允許在其他認證的內容中執行任何 DSC 資源。</span><span class="sxs-lookup"><span data-stu-id="4246f-134">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="4246f-135">如需詳細資訊，請參閱[搭配 DSC 資源使用認證](../../../configurations/runasuser.md)。</span><span class="sxs-lookup"><span data-stu-id="4246f-135">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="4246f-136">範例</span><span class="sxs-lookup"><span data-stu-id="4246f-136">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```