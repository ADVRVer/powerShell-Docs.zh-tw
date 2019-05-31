---
ms.date: 06/12/2017
keywords: wmf,powershell,設定
title: 解除安裝 WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855463"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="bd3da-103">解除安裝指示</span><span class="sxs-lookup"><span data-stu-id="bd3da-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="bd3da-104">使用 [命令提示字元]</span><span class="sxs-lookup"><span data-stu-id="bd3da-104">Using Command Prompt</span></span>

1. <span data-ttu-id="bd3da-105">開啟 **[命令提示字元]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="bd3da-106">執行 [Windows Update 獨立啟動器](https://support.microsoft.com/en-us/kb/934307)，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="bd3da-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="bd3da-107">在 Windows Server 2012 R2 和 Windows 8.1 上：</span><span class="sxs-lookup"><span data-stu-id="bd3da-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="bd3da-108">在 Windows Server 2012 上：</span><span class="sxs-lookup"><span data-stu-id="bd3da-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="bd3da-109">在 Windows Server 2008 R2 SP1 和 Windows 7 SP1 上：</span><span class="sxs-lookup"><span data-stu-id="bd3da-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="bd3da-110">使用 [控制台]</span><span class="sxs-lookup"><span data-stu-id="bd3da-110">Using Control Panel</span></span>

1. <span data-ttu-id="bd3da-111">開啟 **[控制台]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="bd3da-112">開啟 **[程式集]**，然後開啟 **[解除安裝程式]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="bd3da-113">按一下 **[檢視安裝的更新]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="bd3da-114">從已安裝的更新清單中選取 **[Windows Management Framework 5.0]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="bd3da-115">這會對應到 *KB3134758*、*KB3134759* 或 *KB3134760*。</span><span class="sxs-lookup"><span data-stu-id="bd3da-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="bd3da-116">按一下 **[解除安裝]**。</span><span class="sxs-lookup"><span data-stu-id="bd3da-116">Click **Uninstall.**</span></span>