---
ms.date: 06/12/2017
keywords: dsc,powershell,設定,安裝
title: 偵錯 DSC 資源
ms.openlocfilehash: c088e13a25ba31ceebaf52b2d24b5d32b96ae2fc
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954255"
---
# <a name="debugging-dsc-resources"></a><span data-ttu-id="00e2b-103">偵錯 DSC 資源</span><span class="sxs-lookup"><span data-stu-id="00e2b-103">Debugging DSC resources</span></span>

> <span data-ttu-id="00e2b-104">適用於：Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="00e2b-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="00e2b-105">在 PowerShell 5.0 中，預期狀態設定 (DSC) 引進了新功能，可讓您將 DSC 資源當作已套用的設定偵錯。</span><span class="sxs-lookup"><span data-stu-id="00e2b-105">In PowerShell 5.0, a new feature was introduced in Desired State Configuration (DSC) that allows you to debug a DSC resource as a configuration is being applied.</span></span>

## <a name="enabling-dsc-debugging"></a><span data-ttu-id="00e2b-106">啟用 DSC 偵錯</span><span class="sxs-lookup"><span data-stu-id="00e2b-106">Enabling DSC debugging</span></span>
<span data-ttu-id="00e2b-107">偵錯資源之前，您必須先呼叫 [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) Cmdlet 啟用偵錯。</span><span class="sxs-lookup"><span data-stu-id="00e2b-107">Before you can debug a resource, you have to enable debugging by calling the [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) cmdlet.</span></span>
<span data-ttu-id="00e2b-108">這個 Cmdlet 使用強制參數 **BreakAll**。</span><span class="sxs-lookup"><span data-stu-id="00e2b-108">This cmdlet takes a mandatory parameter, **BreakAll**.</span></span>

<span data-ttu-id="00e2b-109">您可以查看呼叫 [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager) 的結果，確認是否已啟用偵錯。</span><span class="sxs-lookup"><span data-stu-id="00e2b-109">You can verify that debugging has been enabled by looking at the result of a call to [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span></span>

<span data-ttu-id="00e2b-110">下列 PowerShell 輸出會顯示啟用偵錯的結果：</span><span class="sxs-lookup"><span data-stu-id="00e2b-110">The following PowerShell output shows the result of enabling debugging:</span></span>


```powershell
PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
NONE

PS C:\DebugTest> Enable-DscDebug -BreakAll

PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
ForceModuleImport
ResourceScriptBreakAll

PS C:\DebugTest>
```


## <a name="starting-a-configuration-with-debug-enabled"></a><span data-ttu-id="00e2b-111">啟動啟用偵錯的設定</span><span class="sxs-lookup"><span data-stu-id="00e2b-111">Starting a configuration with debug enabled</span></span>
<span data-ttu-id="00e2b-112">若要偵錯 DSC 資源，您要啟動設定呼叫該資源。</span><span class="sxs-lookup"><span data-stu-id="00e2b-112">To debug a DSC resource, you start a configuration that calls that resource.</span></span>
<span data-ttu-id="00e2b-113">本例中，我們會探討呼叫 **WindowsFeature** 資源的簡單設定，確定已安裝 "WindowsPowerShellWebAccess" 功能：</span><span class="sxs-lookup"><span data-stu-id="00e2b-113">For this example, we'll look at a simple configuration that calls the **WindowsFeature** resource to ensure that the "WindowsPowerShellWebAccess" feature is installed:</span></span>

```powershell
Configuration PSWebAccess
    {
    Import-DscResource -ModuleName 'PsDesiredStateConfiguration'
    Node localhost
        {
        WindowsFeature PSWA
            {
            Name = 'WindowsPowerShellWebAccess'
            Ensure = 'Present'
            }
        }
    }
PSWebAccess
```
<span data-ttu-id="00e2b-114">編譯設定之後，再呼叫 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) 加以啟動。</span><span class="sxs-lookup"><span data-stu-id="00e2b-114">After compiling the configuration, start it by calling [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span></span>
<span data-ttu-id="00e2b-115">設定停止的時機為本機設定管理員 (LCM) 叫入設定的第一個資源。</span><span class="sxs-lookup"><span data-stu-id="00e2b-115">The configuration will stop when the Local Configuration Manager (LCM) calls into the first resource in the configuration.</span></span>
<span data-ttu-id="00e2b-116">如果使用 `-Verbose` 和 `-Wait` 參數，輸出會顯示您需要輸入的程式行以開始偵錯。</span><span class="sxs-lookup"><span data-stu-id="00e2b-116">If you use the `-Verbose` and `-Wait` parameters, the output displays the lines you need to enter to start debugging.</span></span>

```powershell
Start-DscConfiguration .\PSWebAccess -Wait -Verbose
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfiguration
Manager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Set      ]
WARNING: [TEST-SRV]:                            [DSCEngine] Warning LCM is in Debug 'ResourceScriptBreakAll' mode.  Resource script processing will
be stopped to wait for PowerShell script debugger to attach.
VERBOSE: [TEST-SRV]:                            [DSCEngine] Importing the module C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateCo
nfiguration\DscResources\MSFT_RoleResource\MSFT_RoleResource.psm1 in force mode.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Resource ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]: LCM:  [ Start  Test     ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]:                            [[WindowsFeature]PSWA] Importing the module MSFT_RoleResource in force mode.
WARNING: [TEST-SRV]:                            [[WindowsFeature]PSWA] Resource is waiting for PowerShell script debugger to attach.
Use the following commands to begin debugging this resource script:
Enter-PSSession -ComputerName TEST-SRV -Credential <credentials>
Enter-PSHostProcess -Id 9000 -AppDomainName DscPsPluginWkr_AppDomain
Debug-Runspace -Id 9
```
<span data-ttu-id="00e2b-117">此時，LCM 已呼叫資源且來到第一個中斷點。</span><span class="sxs-lookup"><span data-stu-id="00e2b-117">At this point, the LCM has called the resource, and come to the first break point.</span></span>
<span data-ttu-id="00e2b-118">輸出中的最後三行會示範如何附加至處理程序，並開始偵錯資源指令碼。</span><span class="sxs-lookup"><span data-stu-id="00e2b-118">The last three lines in the output show you how to attach to the process and start debugging the resource script.</span></span>

## <a name="debugging-the-resource-script"></a><span data-ttu-id="00e2b-119">偵錯資源指令碼</span><span class="sxs-lookup"><span data-stu-id="00e2b-119">Debugging the resource script</span></span>

<span data-ttu-id="00e2b-120">啟動 PowerShell ISE 的新執行個體。</span><span class="sxs-lookup"><span data-stu-id="00e2b-120">Start a new instance of the PowerShell ISE.</span></span>
<span data-ttu-id="00e2b-121">在主控台窗格中，輸入 `Start-DscConfiguration` 輸出的最後三行輸出作為命令，將 `<credentials>` 替換成有效的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="00e2b-121">In the console pane, enter the last three lines of output from the `Start-DscConfiguration` output as commands, replacing `<credentials>` with valid user credentials.</span></span>
<span data-ttu-id="00e2b-122">您現在應該會看到類似這樣的提示︰</span><span class="sxs-lookup"><span data-stu-id="00e2b-122">You should now see a prompt that looks similar to:</span></span>

```powershell
[TEST-SRV]: [DBG]: [Process:9000]: [RemoteHost]: PS C:\DebugTest>>
```

<span data-ttu-id="00e2b-123">此資源指令碼會在指令碼窗格中開啟，且偵錯工具會停在 **Test-TargetResource** 函式的第一行 (以類別為基礎之資源的 **Test()** 方法)。</span><span class="sxs-lookup"><span data-stu-id="00e2b-123">The resource script will open in the script pane, and the debugger is stopped at the first line of the **Test-TargetResource** function (the **Test()** method of a class-based resource).</span></span>
<span data-ttu-id="00e2b-124">現在您可以在 ISE 中使用偵錯命令逐步執行資源指令碼、查看變數值、檢視呼叫堆疊，並執行其他工作。</span><span class="sxs-lookup"><span data-stu-id="00e2b-124">Now you can use the debug commands in the ISE to step through the resource script, look at variable values, view the call stack, and so on.</span></span> <span data-ttu-id="00e2b-125">請記住，資源指令碼 (或類別) 中的每一行均已設為中斷點。</span><span class="sxs-lookup"><span data-stu-id="00e2b-125">Remember that every line in the resource script (or class) is set as a break point.</span></span>

## <a name="disabling-dsc-debugging"></a><span data-ttu-id="00e2b-126">停用 DSC 偵錯</span><span class="sxs-lookup"><span data-stu-id="00e2b-126">Disabling DSC debugging</span></span>

<span data-ttu-id="00e2b-127">呼叫 [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) 後，所有對 [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) 的呼叫將會導致設定中斷並進入偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="00e2b-127">After calling [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug), all calls to [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) will result in the configuration breaking into the debugger.</span></span> <span data-ttu-id="00e2b-128">若要使設定正常執行，您必須透過呼叫 [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug) Cmdlet 來停用偵錯。</span><span class="sxs-lookup"><span data-stu-id="00e2b-128">To allow configurations to run normally, you must disable debugging by calling the [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug) cmdlet.</span></span>

><span data-ttu-id="00e2b-129">**注意：** 重新開機不會變更 LCM 的偵錯狀態。</span><span class="sxs-lookup"><span data-stu-id="00e2b-129">**Note:** Rebooting does not change the debug state of the LCM.</span></span> <span data-ttu-id="00e2b-130">若啟用偵錯，則重新開機後啟動設定時仍然會中斷並進入偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="00e2b-130">If debugging is enabled, starting a configuration will still break into the debugger after a reboot.</span></span>

## <a name="see-also"></a><span data-ttu-id="00e2b-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="00e2b-131">See Also</span></span>

- [<span data-ttu-id="00e2b-132">撰寫自訂的 DSC 資源與 MOF</span><span class="sxs-lookup"><span data-stu-id="00e2b-132">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="00e2b-133">使用 PowerShell 類別撰寫自訂的 DSC 資源</span><span class="sxs-lookup"><span data-stu-id="00e2b-133">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)