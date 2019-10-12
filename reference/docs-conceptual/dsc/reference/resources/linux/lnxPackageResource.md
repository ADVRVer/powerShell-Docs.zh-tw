---
ms.date: 09/20/2019
keywords: dsc,powershell,設定,安裝
title: DSC for Linux nxPackage 資源
ms.openlocfilehash: 4091cbbd5e34a84b9011870da4bda93281378347
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954815"
---
# <a name="dsc-for-linux-nxpackage-resource"></a><span data-ttu-id="724ac-103">DSC for Linux nxPackage 資源</span><span class="sxs-lookup"><span data-stu-id="724ac-103">DSC for Linux nxPackage Resource</span></span>

<span data-ttu-id="724ac-104">PowerShell 預期狀態設定 (DSC) 的 **nxPackage** 資源會提供一個機制，在 Linux 節點管理套件。</span><span class="sxs-lookup"><span data-stu-id="724ac-104">The **nxPackage** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage packages on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="724ac-105">語法</span><span class="sxs-lookup"><span data-stu-id="724ac-105">Syntax</span></span>

```Syntax
nxPackage <string> #ResourceName
{
    Name = <string>
    [ PackageManager = <string> { Yum | Apt | Zypper } ]
    [ PackageGroup = <bool>]
    [ Arguments = <string> ]
    [ ReturnCode = <uint32> ]
    [ FilePath = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="724ac-106">Properties</span><span class="sxs-lookup"><span data-stu-id="724ac-106">Properties</span></span>

|<span data-ttu-id="724ac-107">屬性</span><span class="sxs-lookup"><span data-stu-id="724ac-107">Property</span></span> |<span data-ttu-id="724ac-108">描述</span><span class="sxs-lookup"><span data-stu-id="724ac-108">Description</span></span> |
|---|---|
|<span data-ttu-id="724ac-109">名稱</span><span class="sxs-lookup"><span data-stu-id="724ac-109">Name</span></span> |<span data-ttu-id="724ac-110">您要確保其特定狀態的套件名稱。</span><span class="sxs-lookup"><span data-stu-id="724ac-110">The name of the package for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="724ac-111">PackageManager</span><span class="sxs-lookup"><span data-stu-id="724ac-111">PackageManager</span></span> |<span data-ttu-id="724ac-112">支援的值為 **yum**、**apt** 和 **zypper**。</span><span class="sxs-lookup"><span data-stu-id="724ac-112">Supported values are **yum**, **apt**, and **zypper**.</span></span> <span data-ttu-id="724ac-113">指定安裝套件時所使用的套件管理員。</span><span class="sxs-lookup"><span data-stu-id="724ac-113">Specifies the package manager to use when installing packages.</span></span> <span data-ttu-id="724ac-114">如果 **FilePath** 已指定，則使用提供的路徑，以安裝套件。</span><span class="sxs-lookup"><span data-stu-id="724ac-114">If **FilePath** is specified, the provided path will be used to install the package.</span></span> <span data-ttu-id="724ac-115">否則，套件管理員將用於從預先設定的儲存機制安裝套件。</span><span class="sxs-lookup"><span data-stu-id="724ac-115">Otherwise, a Package Manager will be used to install the package from a pre-configured repository.</span></span> <span data-ttu-id="724ac-116">如果沒有提供 **PackageManager** 或 **FilePath**，則會使用系統的預設套件管理員。</span><span class="sxs-lookup"><span data-stu-id="724ac-116">If neither **PackageManager** nor **FilePath** are provided, the default package manager for the system will be used.</span></span> |
|<span data-ttu-id="724ac-117">PackageGroup</span><span class="sxs-lookup"><span data-stu-id="724ac-117">PackageGroup</span></span> |<span data-ttu-id="724ac-118">若為 `$true`，則 **Name** 預計會是套件群組的名稱，用以搭配 **PackageManager** 群組使用。</span><span class="sxs-lookup"><span data-stu-id="724ac-118">If `$true`, the **Name** is expected to be the name of a package group for use with a **PackageManager**.</span></span> <span data-ttu-id="724ac-119">**PackageGroup** 在提供 **FilePath** 時無效。</span><span class="sxs-lookup"><span data-stu-id="724ac-119">**PackageGroup** is not valid when providing a **FilePath**.</span></span> |
|<span data-ttu-id="724ac-120">引數</span><span class="sxs-lookup"><span data-stu-id="724ac-120">Arguments</span></span> |<span data-ttu-id="724ac-121">將傳遞至套件的引數字串，與所提供者完全相同。</span><span class="sxs-lookup"><span data-stu-id="724ac-121">A string of arguments that will be passed to the package exactly as provided.</span></span> |
|<span data-ttu-id="724ac-122">ReturnCode</span><span class="sxs-lookup"><span data-stu-id="724ac-122">ReturnCode</span></span> |<span data-ttu-id="724ac-123">預期的傳回碼。</span><span class="sxs-lookup"><span data-stu-id="724ac-123">The expected return code.</span></span> <span data-ttu-id="724ac-124">如果實際的傳回碼不符這裡提供的預期值，此設定就會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="724ac-124">If the actual return code does not match the expected value provided here, the configuration will return an error.</span></span> |
|<span data-ttu-id="724ac-125">FilePath</span><span class="sxs-lookup"><span data-stu-id="724ac-125">FilePath</span></span> |<span data-ttu-id="724ac-126">套件所在的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="724ac-126">The file path where the package resides.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="724ac-127">通用屬性</span><span class="sxs-lookup"><span data-stu-id="724ac-127">Common properties</span></span>

|<span data-ttu-id="724ac-128">屬性</span><span class="sxs-lookup"><span data-stu-id="724ac-128">Property</span></span> |<span data-ttu-id="724ac-129">描述</span><span class="sxs-lookup"><span data-stu-id="724ac-129">Description</span></span> |
|---|---|
|<span data-ttu-id="724ac-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="724ac-130">DependsOn</span></span> |<span data-ttu-id="724ac-131">表示必須先執行另一個資源的設定，再設定這個資源。</span><span class="sxs-lookup"><span data-stu-id="724ac-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="724ac-132">例如，如果第一個想要執行的資源設定指令碼區塊識別碼是 ResourceName，而其類型是 ResourceType，則使用這個屬性的語法就是 `DependsOn = "[ResourceType]ResourceName"`。</span><span class="sxs-lookup"><span data-stu-id="724ac-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="724ac-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="724ac-133">Ensure</span></span> |<span data-ttu-id="724ac-134">決定是否要檢查套件存在。</span><span class="sxs-lookup"><span data-stu-id="724ac-134">Determines whether to check if the package exists.</span></span> <span data-ttu-id="724ac-135">將此屬性設定為 **Present** 以確保套件存在。</span><span class="sxs-lookup"><span data-stu-id="724ac-135">Set this property to **Present** to ensure the package exists.</span></span> <span data-ttu-id="724ac-136">將其設定為 **Absent** 以確保此套件不存在。</span><span class="sxs-lookup"><span data-stu-id="724ac-136">Set it to **Absent** to ensure the package does not exist.</span></span> <span data-ttu-id="724ac-137">預設值為 **Present**。</span><span class="sxs-lookup"><span data-stu-id="724ac-137">The default value is **Present**.</span></span> |

## <a name="example"></a><span data-ttu-id="724ac-138">範例</span><span class="sxs-lookup"><span data-stu-id="724ac-138">Example</span></span>

<span data-ttu-id="724ac-139">下列範例會確保名為 "httpd" 的套件已使用 "Yum" 套件管理員安裝在 Linux 電腦上。</span><span class="sxs-lookup"><span data-stu-id="724ac-139">The following example ensures that the package named "httpd" is installed on a Linux computer, using the "Yum" package manager.</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxPackage httpd
    {
        Name = "httpd"
        Ensure = "Present"
        PackageManager = "Yum"
    }
}
```