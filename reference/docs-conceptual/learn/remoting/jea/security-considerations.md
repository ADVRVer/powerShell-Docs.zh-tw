---
ms.date: 07/10/2019
keywords: jea,powershell,安全性
title: JEA 安全性考量
ms.openlocfilehash: befc24fec368c4f6d60477daf63bf17e9431133e
ms.sourcegitcommit: e894ed833cef57967cdaf002f8c883f66864e836
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2019
ms.locfileid: "70017769"
---
# <a name="jea-security-considerations"></a><span data-ttu-id="60ddb-103">JEA 安全性考量</span><span class="sxs-lookup"><span data-stu-id="60ddb-103">JEA Security Considerations</span></span>

<span data-ttu-id="60ddb-104">JEA 可協助您減少電腦上的永久系統管理員數目來改善安全性的態勢。</span><span class="sxs-lookup"><span data-stu-id="60ddb-104">JEA helps you improve your security posture by reducing the number of permanent administrators on your machines.</span></span> <span data-ttu-id="60ddb-105">JEA 使用 PowerShell 工作階段設定建立新的進入點，供使用者管理系統。</span><span class="sxs-lookup"><span data-stu-id="60ddb-105">JEA uses a PowerShell session configuration to create a new entry point for users to manage the system.</span></span> <span data-ttu-id="60ddb-106">需要提升電腦存取權 (但非無限) 以執行系統管理工作的使用者，可獲授與 JEA 端點的存取權。</span><span class="sxs-lookup"><span data-stu-id="60ddb-106">Users who need elevated, but not unlimited, access to the machine to do administrative tasks can be granted access to the JEA endpoint.</span></span> <span data-ttu-id="60ddb-107">因為 JEA 允許這些使用者不必有完整的系統管理員存取權即可執行系統管理命令，您可以將這些使用者從高度權限的安全性群組中移除。</span><span class="sxs-lookup"><span data-stu-id="60ddb-107">Since JEA allows these users to run admin commands without having full admin access, you can then remove those users from highly privileged security groups.</span></span>

## <a name="run-as-account"></a><span data-ttu-id="60ddb-108">執行身分帳戶</span><span class="sxs-lookup"><span data-stu-id="60ddb-108">Run-As account</span></span>

<span data-ttu-id="60ddb-109">每個 JEA 端點都有指定的**執行身分**帳戶。</span><span class="sxs-lookup"><span data-stu-id="60ddb-109">Each JEA endpoint has a designated **run-as** account.</span></span> <span data-ttu-id="60ddb-110">這是執行連線使用者動作的帳戶。</span><span class="sxs-lookup"><span data-stu-id="60ddb-110">This is the account under which the connecting user's actions are executed.</span></span> <span data-ttu-id="60ddb-111">此帳戶是可在[工作階段設定檔](session-configurations.md)中設定，且您選擇的帳戶與端點的安全性有很大的關係。</span><span class="sxs-lookup"><span data-stu-id="60ddb-111">This account is configurable in the [session configuration file](session-configurations.md), and the account you choose has a significant bearing on the security of your endpoint.</span></span>

<span data-ttu-id="60ddb-112">**虛擬帳戶**是設定**執行身分**帳戶的建議方式。</span><span class="sxs-lookup"><span data-stu-id="60ddb-112">**Virtual accounts** are the recommended way of configuring the **run-as** account.</span></span> <span data-ttu-id="60ddb-113">虛擬帳戶是一次性、暫時的本機帳戶，針對連線使用者而建立，以便在其 JEA 工作階段期間使用。</span><span class="sxs-lookup"><span data-stu-id="60ddb-113">Virtual accounts are one-time, temporary local accounts that are created for the connecting user to use during the duration of their JEA session.</span></span> <span data-ttu-id="60ddb-114">他們的工作階段一終止，虛擬帳戶便會損毀，無法再使用。</span><span class="sxs-lookup"><span data-stu-id="60ddb-114">As soon as their session is terminated, the virtual account is destroyed and can't be used anymore.</span></span> <span data-ttu-id="60ddb-115">連線的使用者不知道虛擬帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="60ddb-115">The connecting user doesn't know the credentials for the virtual account.</span></span> <span data-ttu-id="60ddb-116">您無法使用虛擬帳戶透過遠端桌面或未受限制的 PowerShell 端點等其他方式來存取系統。</span><span class="sxs-lookup"><span data-stu-id="60ddb-116">The virtual account can't be used to access the system via other means like Remote Desktop or an unconstrained PowerShell endpoint.</span></span>

<span data-ttu-id="60ddb-117">根據預設，虛擬帳戶屬於電腦上的本機 **Administrators** 群組。</span><span class="sxs-lookup"><span data-stu-id="60ddb-117">By default, virtual accounts belong to the local **Administrators** group on the machine.</span></span> <span data-ttu-id="60ddb-118">這可讓他們有完整權限可管理系統上的任何資源，但沒有權限來管理網路上的資源。</span><span class="sxs-lookup"><span data-stu-id="60ddb-118">This gives them full rights to manage anything on the system, but no rights to manage resources on the network.</span></span>
<span data-ttu-id="60ddb-119">向其他電腦進行驗證時，使用者內容會是本機電腦帳戶，而不是虛擬帳戶。</span><span class="sxs-lookup"><span data-stu-id="60ddb-119">When authenticating with other machines, the user context is that of the local computer account, not the virtual account.</span></span>

<span data-ttu-id="60ddb-120">網域控制站是特殊案例，因為沒有本機 **Administrators** 群組。</span><span class="sxs-lookup"><span data-stu-id="60ddb-120">Domain controllers are a special case since there isn't a local **Administrators** group.</span></span> <span data-ttu-id="60ddb-121">但虛擬帳戶屬於 **Domain Admins**，且可以管理網域控制站的目錄服務。</span><span class="sxs-lookup"><span data-stu-id="60ddb-121">Instead, virtual accounts belong to **Domain Admins** and can manage the directory services on the domain controller.</span></span> <span data-ttu-id="60ddb-122">網域身分識別仍然限用於 JEA 工作階段具現化所在的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="60ddb-122">The domain identity is still restricted for use on the domain controller where the JEA session was instantiated.</span></span> <span data-ttu-id="60ddb-123">所有網路存取似乎都改來自網域控制站電腦物件。</span><span class="sxs-lookup"><span data-stu-id="60ddb-123">Any network access appears to come from the domain controller computer object instead.</span></span>

<span data-ttu-id="60ddb-124">在這兩種情況下，您可以明確地定義虛擬帳戶所屬的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="60ddb-124">In both cases, you may explicitly define which security groups the virtual account belongs to.</span></span> <span data-ttu-id="60ddb-125">當工作不需本機或網域系統管理員權限也能執行時，會是較佳的做法。</span><span class="sxs-lookup"><span data-stu-id="60ddb-125">This is a good practice when the task can be done without local or domain admin privileges.</span></span> <span data-ttu-id="60ddb-126">如果您已經為系統管理員定義安全性群組，請將虛擬帳戶成員資格授與該群組。</span><span class="sxs-lookup"><span data-stu-id="60ddb-126">If you already have a security group defined for your admins, grant the virtual account membership to that group.</span></span> <span data-ttu-id="60ddb-127">虛擬帳戶群組成員資格僅限於工作站和成員伺服器的本機安全性群組。</span><span class="sxs-lookup"><span data-stu-id="60ddb-127">Virtual account group membership is limited to local security groups on workstation and member servers.</span></span> <span data-ttu-id="60ddb-128">在網域控制站上，虛擬帳戶必須是網域安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="60ddb-128">On domain controllers, virtual accounts must be members of domain security groups.</span></span>
<span data-ttu-id="60ddb-129">虛擬帳戶新增至一或多個安全性群組之後，即不再屬於預設群組 (本機或網域系統管理員)。</span><span class="sxs-lookup"><span data-stu-id="60ddb-129">Once the virtual account has been added to one or more security groups, it no longer belongs to the default groups (local or domain admins).</span></span>

<span data-ttu-id="60ddb-130">下表摘列虛擬帳戶可能的設定選項和結果權限：</span><span class="sxs-lookup"><span data-stu-id="60ddb-130">The following table summarizes the possible configuration options and resulting permissions for virtual accounts:</span></span>

|        <span data-ttu-id="60ddb-131">電腦類型</span><span class="sxs-lookup"><span data-stu-id="60ddb-131">Computer type</span></span>         | <span data-ttu-id="60ddb-132">虛擬帳戶群組設定</span><span class="sxs-lookup"><span data-stu-id="60ddb-132">Virtual account group configuration</span></span> |                   <span data-ttu-id="60ddb-133">本機使用者內容</span><span class="sxs-lookup"><span data-stu-id="60ddb-133">Local user context</span></span>                    | <span data-ttu-id="60ddb-134">網路使用者內容</span><span class="sxs-lookup"><span data-stu-id="60ddb-134">Network user context</span></span> |
| ---------------------------- | ----------------------------------- | ------------------------------------------------------- | -------------------- |
| <span data-ttu-id="60ddb-135">網域控制站</span><span class="sxs-lookup"><span data-stu-id="60ddb-135">Domain controller</span></span>            | <span data-ttu-id="60ddb-136">Default</span><span class="sxs-lookup"><span data-stu-id="60ddb-136">Default</span></span>                             | <span data-ttu-id="60ddb-137">網域使用者，'*DOMAIN*\Domain Admins' 的成員</span><span class="sxs-lookup"><span data-stu-id="60ddb-137">Domain user, member of '*DOMAIN*\Domain Admins'</span></span>         | <span data-ttu-id="60ddb-138">電腦帳戶</span><span class="sxs-lookup"><span data-stu-id="60ddb-138">Computer account</span></span>     |
| <span data-ttu-id="60ddb-139">網域控制站</span><span class="sxs-lookup"><span data-stu-id="60ddb-139">Domain controller</span></span>            | <span data-ttu-id="60ddb-140">網域群組 A 和 B</span><span class="sxs-lookup"><span data-stu-id="60ddb-140">Domain groups A and B</span></span>               | <span data-ttu-id="60ddb-141">網域使用者，'*DOMAIN*\A', '*DOMAIN*\B' 的成員</span><span class="sxs-lookup"><span data-stu-id="60ddb-141">Domain user, member of '*DOMAIN*\A', '*DOMAIN*\B'</span></span>       | <span data-ttu-id="60ddb-142">電腦帳戶</span><span class="sxs-lookup"><span data-stu-id="60ddb-142">Computer account</span></span>     |
| <span data-ttu-id="60ddb-143">成員伺服器或工作站</span><span class="sxs-lookup"><span data-stu-id="60ddb-143">Member server or workstation</span></span> | <span data-ttu-id="60ddb-144">Default</span><span class="sxs-lookup"><span data-stu-id="60ddb-144">Default</span></span>                             | <span data-ttu-id="60ddb-145">本機使用者，'*BUILTIN*\Administrators' 的成員</span><span class="sxs-lookup"><span data-stu-id="60ddb-145">Local user, member of '*BUILTIN*\Administrators'</span></span>        | <span data-ttu-id="60ddb-146">電腦帳戶</span><span class="sxs-lookup"><span data-stu-id="60ddb-146">Computer account</span></span>     |
| <span data-ttu-id="60ddb-147">成員伺服器或工作站</span><span class="sxs-lookup"><span data-stu-id="60ddb-147">Member server or workstation</span></span> | <span data-ttu-id="60ddb-148">本機群組 C 和 D</span><span class="sxs-lookup"><span data-stu-id="60ddb-148">Local groups C and D</span></span>                | <span data-ttu-id="60ddb-149">本機使用者，'*COMPUTER*\C' 和 '*COMPUTER*\D' 的成員</span><span class="sxs-lookup"><span data-stu-id="60ddb-149">Local user, member of '*COMPUTER*\C' and '*COMPUTER*\D'</span></span> | <span data-ttu-id="60ddb-150">電腦帳戶</span><span class="sxs-lookup"><span data-stu-id="60ddb-150">Computer account</span></span>     |

<span data-ttu-id="60ddb-151">當您查看安全性稽核事件與應用程式事件記錄檔時，您會看到每個 JEA 使用者工作階段都有唯一的虛擬帳戶。</span><span class="sxs-lookup"><span data-stu-id="60ddb-151">When you look at security audit events and application event logs, you see that each JEA user session has a unique virtual account.</span></span> <span data-ttu-id="60ddb-152">這個唯一帳戶可協助您從 JEA 端點中使用者動作回溯到執行命令的原始使用者。</span><span class="sxs-lookup"><span data-stu-id="60ddb-152">This unique account helps you track user actions in a JEA endpoint back to the original user who ran the command.</span></span> <span data-ttu-id="60ddb-153">虛擬帳戶名稱遵循 `WinRM Virtual Users\WinRM_VA_<ACCOUNTNUMBER>_<DOMAIN>_<sAMAccountName>` 格式。例如，如果網域 **Contoso** 中使用者 **Alice** 重新啟動 JEA 端點中的服務，則與任何服務控制管理員事件建立關聯的使用者名稱會是 `WinRM Virtual Users\WinRM_VA_1_contoso_alice`。</span><span class="sxs-lookup"><span data-stu-id="60ddb-153">Virtual account names follow the format `WinRM Virtual Users\WinRM_VA_<ACCOUNTNUMBER>_<DOMAIN>_<sAMAccountName>` For example, if user **Alice** in domain **Contoso** restarts a service in a JEA endpoint, the username associated with any service control manager events would be `WinRM Virtual Users\WinRM_VA_1_contoso_alice`.</span></span>

<span data-ttu-id="60ddb-154">**群組受控服務帳戶 (gMSA)** 適用於成員伺服器需要在 JEA 工作階段中存取網路資源時。</span><span class="sxs-lookup"><span data-stu-id="60ddb-154">**Group-managed service accounts (gMSAs)** are useful when a member server needs to have access to network resources in the JEA session.</span></span> <span data-ttu-id="60ddb-155">例如，使用 JEA 端點來控制不同電腦上所裝載的 REST API 服務時。</span><span class="sxs-lookup"><span data-stu-id="60ddb-155">For example, when a JEA endpoint is used to control access to a REST API service hosted on a different machine.</span></span> <span data-ttu-id="60ddb-156">輕鬆撰寫函式來叫用 REST API，但您需要有網路識別身分才能使用 API 驗證身分。</span><span class="sxs-lookup"><span data-stu-id="60ddb-156">It's easy to write functions to invoke the REST APIs, but you need a network identity to authenticate with the API.</span></span> <span data-ttu-id="60ddb-157">使用群組受控服務帳戶可促成「第二個躍點」，同時仍可控制可以使用帳戶的電腦。</span><span class="sxs-lookup"><span data-stu-id="60ddb-157">Using a group-managed service account makes the second hop possible while maintaining control over which computers can use the account.</span></span> <span data-ttu-id="60ddb-158">gMSA 的有效權限由 gMSA 帳戶所屬安全性群組 (本機或網域) 定義。</span><span class="sxs-lookup"><span data-stu-id="60ddb-158">The effective permissions of the gMSA are defined by the security groups (local or domain) to which the gMSA account belongs.</span></span>

<span data-ttu-id="60ddb-159">JEA 端點設定為使用 gMSA 帳戶之後，所有 JEA 使用者動作似乎都來自相同的 gMSA。</span><span class="sxs-lookup"><span data-stu-id="60ddb-159">When a JEA endpoint is configured to use a gMSA, the actions of all JEA users appear to come from the same gMSA.</span></span> <span data-ttu-id="60ddb-160">從動作回溯到特定使用者的唯一方法，是在 PowerShell 工作階段文字記錄中識別執行的命令集合。</span><span class="sxs-lookup"><span data-stu-id="60ddb-160">The only way to trace actions back to a specific user is to identify the set of commands run in a PowerShell session transcript.</span></span>

<span data-ttu-id="60ddb-161">未指定**執行身分**帳戶時，會使用**傳遞認證**。</span><span class="sxs-lookup"><span data-stu-id="60ddb-161">**Pass-thru credentials** are used when you don't specify a **run-as** account.</span></span> <span data-ttu-id="60ddb-162">PowerShell 使用連線使用者的認證在遠端伺服器上執行命令。</span><span class="sxs-lookup"><span data-stu-id="60ddb-162">PowerShell uses the connecting user's credential to run commands on the remote server.</span></span> <span data-ttu-id="60ddb-163">這需要您授與連線使用者特殊權限管理群組的直接存取權。</span><span class="sxs-lookup"><span data-stu-id="60ddb-163">This requires you to grant the connecting user direct access to privileged management groups.</span></span> <span data-ttu-id="60ddb-164">JEA **不**建議使用此設定。</span><span class="sxs-lookup"><span data-stu-id="60ddb-164">This configuration is **not** recommended for JEA.</span></span> <span data-ttu-id="60ddb-165">如果連線使用者已經有系統管理員權限，他們可以避免使用 JEA 並透過其他未受限制的方式來管理系統。</span><span class="sxs-lookup"><span data-stu-id="60ddb-165">If the connecting user already has admin privileges, they can avoid JEA and manage the system via other, unconstrained means.</span></span> <span data-ttu-id="60ddb-166">如需詳細資訊，請參閱下節中的 [JEA 無法防止系統管理員](#jea-doesnt-protect-against-admins)。</span><span class="sxs-lookup"><span data-stu-id="60ddb-166">For more information, see the section below on how [JEA doesn't protect against admins](#jea-doesnt-protect-against-admins).</span></span>

<span data-ttu-id="60ddb-167">**標準執行身分帳戶**可讓您指定整個 PowerShell 工作階段執行的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="60ddb-167">**Standard run-as accounts** allow you to specify any user account under which the entire PowerShell session runs.</span></span> <span data-ttu-id="60ddb-168">使用固定**執行身分**帳戶 (搭配 `-RunAsCredential` 參數) 的工作階段設定不會察覺 JEA。</span><span class="sxs-lookup"><span data-stu-id="60ddb-168">Session configurations using fixed **run-as** accounts (with the `-RunAsCredential` parameter) aren't JEA-aware.</span></span> <span data-ttu-id="60ddb-169">角色定義不再如預期運作。</span><span class="sxs-lookup"><span data-stu-id="60ddb-169">Role definitions no longer function as expected.</span></span> <span data-ttu-id="60ddb-170">每位獲授權存取端點的使用者皆獲指派相同角色。</span><span class="sxs-lookup"><span data-stu-id="60ddb-170">Every user authorized to access the endpoint is assigned the same role.</span></span>

<span data-ttu-id="60ddb-171">您不應該在 JEA 端點上使用 **RunAsCredential**，因為難以從動作回溯到特定的使用者，且缺乏將使用者對應至角色的支援。</span><span class="sxs-lookup"><span data-stu-id="60ddb-171">You shouldn't use a **RunAsCredential** on a JEA endpoint because it's difficult to trace actions back to specific users and lacks support for mapping users to roles.</span></span>

## <a name="winrm-endpoint-acl"></a><span data-ttu-id="60ddb-172">WinRM 端點 ACL</span><span class="sxs-lookup"><span data-stu-id="60ddb-172">WinRM Endpoint ACL</span></span>

<span data-ttu-id="60ddb-173">如同一般的 PowerShell 遠端端點，每個 JEA 端點都有個別的存取控制清單 (ACL)，可控制誰可以向 JEA 端點驗證身分。</span><span class="sxs-lookup"><span data-stu-id="60ddb-173">As with regular PowerShell remoting endpoints, each JEA endpoint has a separate access control list (ACL) that controls who can authenticate with the JEA endpoint.</span></span> <span data-ttu-id="60ddb-174">如果設定不當，受信任的使用者可能無法存取 JEA 端點，且未受信任的使用者可能取得存取權。</span><span class="sxs-lookup"><span data-stu-id="60ddb-174">If improperly configured, trusted users may not be able to access the JEA endpoint and untrusted users may have access.</span></span> <span data-ttu-id="60ddb-175">WinRM ACL 不會影響將使用者對應至 JEA 角色。</span><span class="sxs-lookup"><span data-stu-id="60ddb-175">The WinRM ACL doesn't affect the mapping of users to JEA roles.</span></span> <span data-ttu-id="60ddb-176">對應是由用來登錄端點的工作階段設定檔 **RoleDefinitions** 欄位所控制。</span><span class="sxs-lookup"><span data-stu-id="60ddb-176">Mapping is controlled by the **RoleDefinitions** field in the session configuration file used to register the endpoint.</span></span>

<span data-ttu-id="60ddb-177">根據預設，當 JEA 端點有多個角色功能時，WinRM ACL 會設定為允許存取所有的對應使用者。</span><span class="sxs-lookup"><span data-stu-id="60ddb-177">By default, when a JEA endpoint has multiple role capabilities, the WinRM ACL is configured to allow access to all mapped users.</span></span> <span data-ttu-id="60ddb-178">例如，使用下列命令設定的 JEA 工作階段，會將完整存取權授與 `CONTOSO\JEA_Lev1` 和 `CONTOSO\JEA_Lev2`。</span><span class="sxs-lookup"><span data-stu-id="60ddb-178">For example, a JEA session configured using the following commands grants full access to `CONTOSO\JEA_Lev1` and `CONTOSO\JEA_Lev2`.</span></span>

```powershell
$roles = @{ 'CONTOSO\JEA_Lev1' = 'Lev1Role'; 'CONTOSO\JEA_Lev2' = 'Lev2Role' }
New-PSSessionConfigurationFile -Path '.\jea.pssc' -SessionType RestrictedRemoteServer -RoleDefinitions $roles -RunAsVirtualAccount
Register-PSSessionConfiguration -Path '.\jea.pssc' -Name 'MyJEAEndpoint'
```

<span data-ttu-id="60ddb-179">您可以使用 [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) Cmdlet 稽核使用者權限。</span><span class="sxs-lookup"><span data-stu-id="60ddb-179">You can audit user permissions with the [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration) cmdlet.</span></span>

```powershell
Get-PSSessionConfiguration -Name 'MyJEAEndpoint' | Select-Object Permission
```

```Output
Permission
----------
CONTOSO\JEA_Lev1 AccessAllowed
CONTOSO\JEA_Lev2 AccessAllowed
```

<span data-ttu-id="60ddb-180">若要變更哪些使用者可以存取，請執行 `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -ShowSecurityDescriptorUI` 以取得互動式提示或執行 `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -SecurityDescriptorSddl <SDDL string>` 來更新權限。</span><span class="sxs-lookup"><span data-stu-id="60ddb-180">To change which users have access, run either `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -ShowSecurityDescriptorUI` for an interactive prompt or `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -SecurityDescriptorSddl <SDDL string>` to update the permissions.</span></span> <span data-ttu-id="60ddb-181">使用者需要至少有「叫用」  權利才能存取 JEA 端點。</span><span class="sxs-lookup"><span data-stu-id="60ddb-181">Users need at least *Invoke* rights to access the JEA endpoint.</span></span>

<span data-ttu-id="60ddb-182">您可建立一個 JEA 端點，不對應至每個具有存取權的使用者已定義角色。</span><span class="sxs-lookup"><span data-stu-id="60ddb-182">It's possible to create a JEA endpoint that doesn't map a defined role to every user that has access.</span></span> <span data-ttu-id="60ddb-183">這些使用者可以啟動 JEA 工作階段，但只能存取預設的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="60ddb-183">These users can start a JEA session, but only have access to the default cmdlets.</span></span> <span data-ttu-id="60ddb-184">您可以藉由執行 `Get-PSSessionCapability` 稽核 JEA 端點中的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="60ddb-184">You can audit user permissions in a JEA endpoint by running `Get-PSSessionCapability`.</span></span> <span data-ttu-id="60ddb-185">如需詳細資訊，請參閱 [JEA 上的稽核和報告](audit-and-report.md)。</span><span class="sxs-lookup"><span data-stu-id="60ddb-185">For more information, see [Auditing and Reporting on JEA](audit-and-report.md).</span></span>

## <a name="least-privilege-roles"></a><span data-ttu-id="60ddb-186">最低權限角色</span><span class="sxs-lookup"><span data-stu-id="60ddb-186">Least privilege roles</span></span>

<span data-ttu-id="60ddb-187">在設計 JEA 角色時，請務必記得在幕後執行的虛擬和群組受控服務帳戶，通常可無限制存取本機電腦。</span><span class="sxs-lookup"><span data-stu-id="60ddb-187">When designing JEA roles, it's important to remember that the virtual and group-managed service accounts running behind the scenes can have unrestricted access to the local machine.</span></span> <span data-ttu-id="60ddb-188">JEA 角色功能可協助限制可在該特殊權限內容中執行的命令和應用程式。</span><span class="sxs-lookup"><span data-stu-id="60ddb-188">JEA role capabilities help limit the commands and applications that can be run in that privileged context.</span></span>
<span data-ttu-id="60ddb-189">設計不當的角色會允許危險命令，可能允許使用者突破 JEA 界限或取得敏感性資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="60ddb-189">Improperly designed roles can allow dangerous commands that may permit a user to break out of the JEA boundaries or obtain access to sensitive information.</span></span>

<span data-ttu-id="60ddb-190">例如，請考慮下列角色功能項目：</span><span class="sxs-lookup"><span data-stu-id="60ddb-190">For example, consider the following role capability entry:</span></span>

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\*-Process'
}
```

<span data-ttu-id="60ddb-191">此角色功能可讓使用者執行任何 PowerShell Cmdlet，並使用來自 **Microsoft.PowerShell.Management** 模組的名詞 **Process**。</span><span class="sxs-lookup"><span data-stu-id="60ddb-191">This role capability allows users to run any PowerShell cmdlet with the noun **Process** from the **Microsoft.PowerShell.Management** module.</span></span> <span data-ttu-id="60ddb-192">使用者可能需要存取像 `Get-Process` 這樣的 Cmdlet 來了解哪些應用程式正在系統上執行，以及存取 `Stop-Process` 來終止任何未回應的應用程式。</span><span class="sxs-lookup"><span data-stu-id="60ddb-192">Users may need to access cmdlets like `Get-Process` to see what applications are running on the system and `Stop-Process` to kill applications that aren't responding.</span></span> <span data-ttu-id="60ddb-193">不過，此項目也允許 `Start-Process`，這可以用來以完整的系統管理員權限啟動任意程式。</span><span class="sxs-lookup"><span data-stu-id="60ddb-193">However, this entry also allows `Start-Process`, which can be used to start up an arbitrary program with full administrator permissions.</span></span> <span data-ttu-id="60ddb-194">程式不需要安裝在本機系統上。</span><span class="sxs-lookup"><span data-stu-id="60ddb-194">The program doesn't need to be installed locally on the system.</span></span> <span data-ttu-id="60ddb-195">已連線的使用者可從授與使用者本機系統管理員權限、執行惡意程式碼及執行其他作業的檔案共用來啟動程式。</span><span class="sxs-lookup"><span data-stu-id="60ddb-195">A connected user could start a program from a file share that gives the user local admin privileges, runs malware, and more.</span></span>

<span data-ttu-id="60ddb-196">這項相同角色功能的更安全版本應該如下︰</span><span class="sxs-lookup"><span data-stu-id="60ddb-196">A more secure version of this same role capability would look like:</span></span>

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\Get-Process', 'Microsoft.PowerShell.Management\Stop-Process'
}
```

<span data-ttu-id="60ddb-197">避免在角色功能中使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="60ddb-197">Avoid using wildcards in role capabilities.</span></span> <span data-ttu-id="60ddb-198">請務必定期[稽核有效的使用者權限](audit-and-report.md#check-effective-rights-for-a-specific-user)，以了解哪些命令可供使用者存取。</span><span class="sxs-lookup"><span data-stu-id="60ddb-198">Be sure to regularly [audit effective user permissions](audit-and-report.md#check-effective-rights-for-a-specific-user) to understand which commands are accessible to the user.</span></span>

## <a name="jea-doesnt-protect-against-admins"></a><span data-ttu-id="60ddb-199">JEA 無法防止系統管理員</span><span class="sxs-lookup"><span data-stu-id="60ddb-199">JEA doesn't protect against admins</span></span>

<span data-ttu-id="60ddb-200">JEA 的核心原則之一是允許非管理員執行一些管理工作。</span><span class="sxs-lookup"><span data-stu-id="60ddb-200">One of the core principles of JEA is that it allows non-admins to do some admin tasks.</span></span> <span data-ttu-id="60ddb-201">JEA 無法防止已有系統管理員權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="60ddb-201">JEA doesn't protect against users who already have administrator privileges.</span></span> <span data-ttu-id="60ddb-202">屬於 **Domain Admins**、本機 **Administrators** 或其他高度權限群組的使用者，可以透過其他方式規避 JEA 防護。</span><span class="sxs-lookup"><span data-stu-id="60ddb-202">Users who belong **Domain Admins**, local **Administrators**, or other highly privileged groups can circumvent JEA's protections via another means.</span></span> <span data-ttu-id="60ddb-203">例如，他們可以使用 RDP 登入、使用遠端 MMC 主控台或連接至未受限制的 PowerShell 端點。</span><span class="sxs-lookup"><span data-stu-id="60ddb-203">For example, they could sign in with RDP, use remote MMC consoles, or connect to unconstrained PowerShell endpoints.</span></span> <span data-ttu-id="60ddb-204">系統上的本機管理員也可以修改 JEA 設定，允許其他使用者或變更角色功能以擴充使用者可以在其 JEA 工作階段中執行的範圍。</span><span class="sxs-lookup"><span data-stu-id="60ddb-204">Also, local admins on a system can modify JEA configurations to allow additional users or change a role capability to extend the scope of what a user can do in their JEA session.</span></span> <span data-ttu-id="60ddb-205">因此務必要評估您的 JEA 使用者擴充權限，看看他們是否有其他方法可取得系統的特殊權限存取。</span><span class="sxs-lookup"><span data-stu-id="60ddb-205">It's important to evaluate your JEA users' extended permissions to see if there are other ways to gain privileged access to the system.</span></span>

<span data-ttu-id="60ddb-206">常見的做法是使用 JEA 進行一般日常維護，且擁有 Just-in-Time 的特殊權限存取管理解決方案，讓使用者在緊急情況下暫時成為本機管理員。</span><span class="sxs-lookup"><span data-stu-id="60ddb-206">A common practice is to use JEA for regular day-to-day maintenance and have a just-in-time, privileged access management solution that allows users to temporarily become local admins in emergency situations.</span></span> <span data-ttu-id="60ddb-207">這有助於確保使用者在系統上不是永久的系統管理員，但如果 (且唯有) 他們完成之工作流程會記錄他們對那些權限的使用，便可以取得那些權限。</span><span class="sxs-lookup"><span data-stu-id="60ddb-207">This helps ensure users aren't permanent admins on the system, but can get those rights if, and only when, they complete a workflow that documents their use of those permissions.</span></span>