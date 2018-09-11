---
ms.date: 08/23/2018
keywords: powershell,cmdlet
title: 了解 PowerShell 管線
ms.assetid: 6be50926-7943-4ef7-9499-4490d72a63fb
ms.openlocfilehash: 3ee03f001668fb24ff9be1ea6ecb3817e319d0ee
ms.sourcegitcommit: 59727f71dc204785a1bcdedc02716d8340a77aeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "43134121"
---
# <a name="understanding-pipelines"></a><span data-ttu-id="bde7e-103">了解管線</span><span class="sxs-lookup"><span data-stu-id="bde7e-103">Understanding pipelines</span></span>

<span data-ttu-id="bde7e-104">管線就像是一系列連接的管道區段。</span><span class="sxs-lookup"><span data-stu-id="bde7e-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="bde7e-105">沿著管線移動的項目會通過每個區段。</span><span class="sxs-lookup"><span data-stu-id="bde7e-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="bde7e-106">若要在 PowerShell 中建立管線，您可以將命令與管道運算子 "|" 連接在一起。</span><span class="sxs-lookup"><span data-stu-id="bde7e-106">To create a pipeline in PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="bde7e-107">每個命令的輸出可作為下一個命令的輸入。</span><span class="sxs-lookup"><span data-stu-id="bde7e-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="bde7e-108">用於管線的標記法類似於其他殼層中所使用的標記法。</span><span class="sxs-lookup"><span data-stu-id="bde7e-108">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="bde7e-109">乍看之下，PowerShell 中的管線差異可能並不明顯。</span><span class="sxs-lookup"><span data-stu-id="bde7e-109">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="bde7e-110">雖然您會在畫面上看到文字，但 PowerShell 會在命令之間使用管線來傳送物件 (而非文字)。</span><span class="sxs-lookup"><span data-stu-id="bde7e-110">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

## <a name="the-powershell-pipeline"></a><span data-ttu-id="bde7e-111">PowerShell 管線</span><span class="sxs-lookup"><span data-stu-id="bde7e-111">The PowerShell pipeline</span></span>

<span data-ttu-id="bde7e-112">管線可說是用於命令列介面中最重要的概念。</span><span class="sxs-lookup"><span data-stu-id="bde7e-112">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="bde7e-113">如果運用得當，管線會減少使用複雜命令所耗費的心力，並且能夠更輕鬆地查看命令的工作流程。</span><span class="sxs-lookup"><span data-stu-id="bde7e-113">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work for the commands.</span></span> <span data-ttu-id="bde7e-114">管線中的每個命令 (稱為管線元素) 會將其輸出逐項目傳遞至管線中的下一個命令。</span><span class="sxs-lookup"><span data-stu-id="bde7e-114">Each command in a pipeline (called a pipeline element) passes its output to the next command in the pipeline, item-by-item.</span></span> <span data-ttu-id="bde7e-115">命令不需要每次處理一個以上的項目。</span><span class="sxs-lookup"><span data-stu-id="bde7e-115">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="bde7e-116">結果就是減少資源耗用量，並能立即開始取得輸出。</span><span class="sxs-lookup"><span data-stu-id="bde7e-116">The result is reduced resource consumption and the ability to begin getting the output immediately.</span></span>

<span data-ttu-id="bde7e-117">例如，如果您使用 `Out-Host` Cmdlet 強制逐頁顯示另一個命令的輸出，則輸出看起來就像畫面上所顯示的一般文字 (分成數頁)：</span><span class="sxs-lookup"><span data-stu-id="bde7e-117">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging
```

```Output
    Directory: C:\WINDOWS\system32

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/12/2018   2:15 AM                0409
d-----        5/13/2018  11:31 PM                1033
d-----        4/11/2018   4:38 PM                AdvancedInstallers
d-----        5/13/2018  11:13 PM                af-ZA
d-----        5/13/2018  11:13 PM                am-et
d-----        4/11/2018   4:38 PM                AppLocker
d-----        5/13/2018  11:31 PM                appmgmt
d-----        7/11/2018   2:05 AM                appraiser
d---s-        4/12/2018   2:20 AM                AppV
d-----        5/13/2018  11:10 PM                ar-SA
d-----        5/13/2018  11:13 PM                as-IN
d-----        8/14/2018   9:03 PM                az-Latn-AZ
d-----        5/13/2018  11:13 PM                be-BY
d-----        5/13/2018  11:10 PM                BestPractices
d-----        5/13/2018  11:10 PM                bg-BG
d-----        5/13/2018  11:13 PM                bn-BD
d-----        5/13/2018  11:13 PM                bn-IN
d-----        8/14/2018   9:03 PM                Boot
d-----        8/14/2018   9:03 PM                bs-Latn-BA
d-----        4/11/2018   4:38 PM                Bthprops
d-----        4/12/2018   2:19 AM                ca-ES
d-----        8/14/2018   9:03 PM                ca-ES-valencia
d-----        5/13/2018  10:46 PM                CatRoot
d-----        8/23/2018   5:07 PM                catroot2
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="bde7e-118">分頁還會降低 CPU 使用率，因為處理控制權會在其已準備好要顯示的完成頁面時移轉給 `Out-Host` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bde7e-118">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="bde7e-119">管線中在它前面的 Cmdlet 會暫停執行，直到輸出的下一個分頁可供使用為止。</span><span class="sxs-lookup"><span data-stu-id="bde7e-119">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

<span data-ttu-id="bde7e-120">您可以看到不同的 Windows 工作管理員監視 PowerShell 所使用的 CPU 和記憶體。</span><span class="sxs-lookup"><span data-stu-id="bde7e-120">You can see the difference Windows Task Manager to monitor CPU and memory used by PowerShell.</span></span> <span data-ttu-id="bde7e-121">執行下列命令：`Get-ChildItem C:\\Windows -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="bde7e-121">Run the following command: `Get-ChildItem C:\\Windows -Recurse`.</span></span> <span data-ttu-id="bde7e-122">將 CPU 和記憶體使用量與這個命令進行比較：`Get-ChildItem C:\\Windows -Recurse | Out-Host -Paging`。</span><span class="sxs-lookup"><span data-stu-id="bde7e-122">Compare the CPU and memory usage to this command: `Get-ChildItem C:\\Windows -Recurse | Out-Host -Paging`.</span></span>

## <a name="objects-in-the-pipeline"></a><span data-ttu-id="bde7e-123">管線中的物件</span><span class="sxs-lookup"><span data-stu-id="bde7e-123">Objects in the pipeline</span></span>

<span data-ttu-id="bde7e-124">當您在 PowerShell 中執行 Cmdlet 時，您會看到文字輸出，這是因為在主控台視窗中必須將物件呈現為文字。</span><span class="sxs-lookup"><span data-stu-id="bde7e-124">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="bde7e-125">文字輸出可能不會顯示要輸出之物件的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="bde7e-125">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="bde7e-126">例如，請考慮 `Get-Location` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bde7e-126">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="bde7e-127">如果您在目前位置是 C 磁碟機的根目錄時執行 `Get-Location`，就會看到下列輸出：</span><span class="sxs-lookup"><span data-stu-id="bde7e-127">If you run `Get-Location` while your current location is the root of the C drive, you see the following output:</span></span>

```
PS> Get-Location

Path
----
C:\
```

<span data-ttu-id="bde7e-128">文字輸出是資訊的摘要，並不是由 `Get-Location` 所傳回之物件的完整呈現。</span><span class="sxs-lookup"><span data-stu-id="bde7e-128">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="bde7e-129">輸出中的標題是由處理序新增的，它會將資料格式化以便在畫面上顯示。</span><span class="sxs-lookup"><span data-stu-id="bde7e-129">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

<span data-ttu-id="bde7e-130">當您使用管線將輸出傳送到 `Get-Member` Cmdlet 時，會取得由 `Get-Location` 所傳回的物件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bde7e-130">When you pipe the output to the `Get-Member` cmdlet you get information about the object returned by `Get-Location`.</span></span>

```powershell
PS> Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="bde7e-131">`Get-Location` 會傳回 **PathInfo** 物件，其中包含目前的路徑與其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bde7e-131">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>