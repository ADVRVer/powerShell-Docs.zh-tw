---
title: 常見的工作流程參數 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5891467-8e13-484d-b7af-32e6bffab35d
caps.latest.revision: 4
ms.openlocfilehash: b2e8f272a82ee03de306fd8eac45e109142f6284
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054793"
---
# <a name="common-workflow-parameters"></a><span data-ttu-id="05d0e-102">常見工作流程參數</span><span class="sxs-lookup"><span data-stu-id="05d0e-102">Common Workflow Parameters</span></span>

<span data-ttu-id="05d0e-103">從 Windows PowerShell cmdlet 產生的工作流程活動的所有活動中都定義幾個常見的參數。</span><span class="sxs-lookup"><span data-stu-id="05d0e-103">A workflow activity generated from a Windows PowerShell cmdlet  defines a number of parameters that common to all activities.</span></span> <span data-ttu-id="05d0e-104">在撰寫期間，讓工作流程作者可以自訂活動，您可以指定這些參數的子集。</span><span class="sxs-lookup"><span data-stu-id="05d0e-104">A subset of these parameters can be specified at authoring time so that workflow authors can customize activities.</span></span> <span data-ttu-id="05d0e-105">使用者可以指定這些參數的另一個子集，呼叫活動時。</span><span class="sxs-lookup"><span data-stu-id="05d0e-105">Another subset of these parameters can be specified by the user when calling the activity.</span></span>

<span data-ttu-id="05d0e-106">常見的工作流程參數分為數個類別，如下所示。</span><span class="sxs-lookup"><span data-stu-id="05d0e-106">The common workflow parameters are grouped into several categories as follows.</span></span>

## <a name="connectivity-parameters"></a><span data-ttu-id="05d0e-107">連線參數</span><span class="sxs-lookup"><span data-stu-id="05d0e-107">Connectivity Parameters</span></span>

|<span data-ttu-id="05d0e-108">名稱</span><span class="sxs-lookup"><span data-stu-id="05d0e-108">Name</span></span>|<span data-ttu-id="05d0e-109">類型</span><span class="sxs-lookup"><span data-stu-id="05d0e-109">Type</span></span>|<span data-ttu-id="05d0e-110">描述</span><span class="sxs-lookup"><span data-stu-id="05d0e-110">Description</span></span>|<span data-ttu-id="05d0e-111">您可指定在執行階段的使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="05d0e-111">Can be specified by end user at execution time?</span></span>|<span data-ttu-id="05d0e-112">您可指定在撰寫期間的工作流程作者嗎？</span><span class="sxs-lookup"><span data-stu-id="05d0e-112">Can be specified by workflow author at authoring time?</span></span>|<span data-ttu-id="05d0e-113">您可指定在具現化的工作流程作者嗎？</span><span class="sxs-lookup"><span data-stu-id="05d0e-113">Can be specified by workflow author at instantiation?</span></span>|
|----------|----------|-----------------|-----------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|<span data-ttu-id="05d0e-114">PSComputerName</span><span class="sxs-lookup"><span data-stu-id="05d0e-114">PSComputerName</span></span>|<span data-ttu-id="05d0e-115">String[]</span><span class="sxs-lookup"><span data-stu-id="05d0e-115">String[]</span></span>|<span data-ttu-id="05d0e-116">要啟動作業的電腦名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="05d0e-116">A list of computer names for which to launch jobs.</span></span>|<span data-ttu-id="05d0e-117">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-117">Yes</span></span>|<span data-ttu-id="05d0e-118">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-118">Yes</span></span>|<span data-ttu-id="05d0e-119">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-119">Yes</span></span>|
|<span data-ttu-id="05d0e-120">PSCredential</span><span class="sxs-lookup"><span data-stu-id="05d0e-120">PSCredential</span></span>|[<span data-ttu-id="05d0e-121">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="05d0e-121">System.Management.Automation.PSCredential</span></span>](/dotnet/api/System.Management.Automation.PSCredential)|<span data-ttu-id="05d0e-122">要使用的驗證認證來登入 PSComputerName 參數所指定的電腦。</span><span class="sxs-lookup"><span data-stu-id="05d0e-122">The authentication credential to use to login to the computers specified by the PSComputerName parameter.</span></span> <span data-ttu-id="05d0e-123">此參數會指定 PSComputerName 時才有效。</span><span class="sxs-lookup"><span data-stu-id="05d0e-123">This parameter is valid only if PSComputerName is specified.</span></span>|<span data-ttu-id="05d0e-124">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-124">Yes</span></span>|<span data-ttu-id="05d0e-125">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-125">Yes</span></span>|<span data-ttu-id="05d0e-126">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-126">Yes</span></span>|
|<span data-ttu-id="05d0e-127">PSPort</span><span class="sxs-lookup"><span data-stu-id="05d0e-127">PSPort</span></span>|<span data-ttu-id="05d0e-128">UInt32</span><span class="sxs-lookup"><span data-stu-id="05d0e-128">UInt32</span></span>|<span data-ttu-id="05d0e-129">要用來執行工作流程的連接埠。</span><span class="sxs-lookup"><span data-stu-id="05d0e-129">The port to be used to run the workflow.</span></span>|<span data-ttu-id="05d0e-130">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-130">Yes</span></span>|<span data-ttu-id="05d0e-131">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-131">Yes</span></span>|<span data-ttu-id="05d0e-132">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-132">Yes</span></span>|
|<span data-ttu-id="05d0e-133">PSUseSSL</span><span class="sxs-lookup"><span data-stu-id="05d0e-133">PSUseSSL</span></span>|<span data-ttu-id="05d0e-134">布林值</span><span class="sxs-lookup"><span data-stu-id="05d0e-134">Boolean</span></span>|<span data-ttu-id="05d0e-135">若要建立安全連線到遠端電腦執行工作流程中使用安全通訊端層 (SSL) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="05d0e-135">Use Secure Sockets Layer (SSL) protocol to establish a secure connection to the remote computer to run the workflow.</span></span>|<span data-ttu-id="05d0e-136">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-136">Yes</span></span>|<span data-ttu-id="05d0e-137">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-137">Yes</span></span>|<span data-ttu-id="05d0e-138">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-138">Yes</span></span>|
|<span data-ttu-id="05d0e-139">PSConfigurationName</span><span class="sxs-lookup"><span data-stu-id="05d0e-139">PSConfigurationName</span></span>|<span data-ttu-id="05d0e-140">String</span><span class="sxs-lookup"><span data-stu-id="05d0e-140">String</span></span>|<span data-ttu-id="05d0e-141">用來執行工作流程工作階段設定。</span><span class="sxs-lookup"><span data-stu-id="05d0e-141">The session configuration used to run the workflow.</span></span>|<span data-ttu-id="05d0e-142">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-142">Yes</span></span>|<span data-ttu-id="05d0e-143">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-143">Yes</span></span>|<span data-ttu-id="05d0e-144">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-144">Yes</span></span>|
|<span data-ttu-id="05d0e-145">PSApplicationName</span><span class="sxs-lookup"><span data-stu-id="05d0e-145">PSApplicationName</span></span>|<span data-ttu-id="05d0e-146">String</span><span class="sxs-lookup"><span data-stu-id="05d0e-146">String</span></span>|<span data-ttu-id="05d0e-147">工作流程執行的連線 URI 的應用程式名稱部分。</span><span class="sxs-lookup"><span data-stu-id="05d0e-147">The application name portion of the connection URI for the workflow execution.</span></span> <span data-ttu-id="05d0e-148">只有在您不使用 ConnectionURI 參數時，請使用此參數。</span><span class="sxs-lookup"><span data-stu-id="05d0e-148">Use this parameter only when you are not using the ConnectionURI parameter.</span></span>|<span data-ttu-id="05d0e-149">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-149">Yes</span></span>|<span data-ttu-id="05d0e-150">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-150">Yes</span></span>|<span data-ttu-id="05d0e-151">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-151">Yes</span></span>|
|<span data-ttu-id="05d0e-152">PSThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="05d0e-152">PSThrottleLimit</span></span>|<span data-ttu-id="05d0e-153">UInt32</span><span class="sxs-lookup"><span data-stu-id="05d0e-153">UInt32</span></span>|<span data-ttu-id="05d0e-154">可執行工作流程建立的並行連線數目上限。</span><span class="sxs-lookup"><span data-stu-id="05d0e-154">The maximum number of concurrent connections that can be established to run the workflow.</span></span>|<span data-ttu-id="05d0e-155">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-155">Yes</span></span>|<span data-ttu-id="05d0e-156">TBD</span><span class="sxs-lookup"><span data-stu-id="05d0e-156">TBD</span></span>|<span data-ttu-id="05d0e-157">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-157">Yes</span></span>|
|<span data-ttu-id="05d0e-158">PSConnectionURI</span><span class="sxs-lookup"><span data-stu-id="05d0e-158">PSConnectionURI</span></span>|<span data-ttu-id="05d0e-159">String[]</span><span class="sxs-lookup"><span data-stu-id="05d0e-159">String[]</span></span>|<span data-ttu-id="05d0e-160">針對用來執行工作流程的互動式工作階段指定端點的完整 Uri 的陣列。</span><span class="sxs-lookup"><span data-stu-id="05d0e-160">An array of fully-qualified URIs that specify the endpoints for the interactive sessions used to run the workflow.</span></span>|<span data-ttu-id="05d0e-161">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-161">Yes</span></span>|<span data-ttu-id="05d0e-162">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-162">Yes</span></span>|<span data-ttu-id="05d0e-163">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-163">Yes</span></span>|
|<span data-ttu-id="05d0e-164">PSAllowRedirection</span><span class="sxs-lookup"><span data-stu-id="05d0e-164">PSAllowRedirection</span></span>|<span data-ttu-id="05d0e-165">布林值</span><span class="sxs-lookup"><span data-stu-id="05d0e-165">Boolean</span></span>|<span data-ttu-id="05d0e-166">指定是否允許這個連接來執行工作流程的替代 URI 的重新導向。</span><span class="sxs-lookup"><span data-stu-id="05d0e-166">Specifies whether to allow redirection of this connection to an alternate URI to run the workflow.</span></span>|<span data-ttu-id="05d0e-167">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-167">Yes</span></span>|<span data-ttu-id="05d0e-168">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-168">Yes</span></span>|<span data-ttu-id="05d0e-169">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-169">Yes</span></span>|
|<span data-ttu-id="05d0e-170">PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="05d0e-170">PSSessionOption</span></span>|[<span data-ttu-id="05d0e-171">System.Management.Automation.Remoting.Pssessionoption</span><span class="sxs-lookup"><span data-stu-id="05d0e-171">System.Management.Automation.Remoting.Pssessionoption</span></span>](/dotnet/api/System.Management.Automation.Remoting.PSSessionOption)|<span data-ttu-id="05d0e-172">用來執行工作流程工作階段的進階的選項。</span><span class="sxs-lookup"><span data-stu-id="05d0e-172">Advanced options for the session used to run the workflow.</span></span>|<span data-ttu-id="05d0e-173">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-173">Yes</span></span>|<span data-ttu-id="05d0e-174">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-174">Yes</span></span>|<span data-ttu-id="05d0e-175">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-175">Yes</span></span>|
|<span data-ttu-id="05d0e-176">PSAuthentication</span><span class="sxs-lookup"><span data-stu-id="05d0e-176">PSAuthentication</span></span>|[<span data-ttu-id="05d0e-177">System.Management.Automation.Runspaces.Authenticationmechanism</span><span class="sxs-lookup"><span data-stu-id="05d0e-177">System.Management.Automation.Runspaces.Authenticationmechanism</span></span>](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)|<span data-ttu-id="05d0e-178">值為[System.Management.Automation.Runspaces.Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism)列舉，指定用來驗證使用者的認證的驗證機制。</span><span class="sxs-lookup"><span data-stu-id="05d0e-178">A value of the [System.Management.Automation.Runspaces.Authenticationmechanism](/dotnet/api/System.Management.Automation.Runspaces.AuthenticationMechanism) enumeration that specifies the authentication mechanism used to authenticate the user's credentials.</span></span>|<span data-ttu-id="05d0e-179">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-179">Yes</span></span>|<span data-ttu-id="05d0e-180">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-180">Yes</span></span>|<span data-ttu-id="05d0e-181">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-181">Yes</span></span>|
|<span data-ttu-id="05d0e-182">PSCertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="05d0e-182">PSCertificateThumbprint</span></span>|<span data-ttu-id="05d0e-183">String</span><span class="sxs-lookup"><span data-stu-id="05d0e-183">String</span></span>|<span data-ttu-id="05d0e-184">數位公開金鑰憑證 (X509) 的可執行工作流程的權限的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="05d0e-184">The digital public key certificate (X509) of a user account that has permission to run the workflow.</span></span>|<span data-ttu-id="05d0e-185">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-185">Yes</span></span>|<span data-ttu-id="05d0e-186">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-186">Yes</span></span>|<span data-ttu-id="05d0e-187">是</span><span class="sxs-lookup"><span data-stu-id="05d0e-187">Yes</span></span>|

### <a name="behavior-parameters"></a><span data-ttu-id="05d0e-188">行為的參數</span><span class="sxs-lookup"><span data-stu-id="05d0e-188">Behavior Parameters</span></span>