---
title: 將資源新增至管理 OData Web 服務 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e620bf6d-76be-47b0-a7a8-f43418f30c60
caps.latest.revision: 6
ms.openlocfilehash: b81a32b867795ae51c3f5308c2f82c31ed2747fa
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858364"
---
# <a name="adding-resources-to-a-management-odata-web-service"></a><span data-ttu-id="83ef0-102">新增資源至 Management OData Web 服務</span><span class="sxs-lookup"><span data-stu-id="83ef0-102">Adding Resources to a Management OData Web Service</span></span>

<span data-ttu-id="83ef0-103">此範例示範如何使用管理 OData 的結構描述設計工具，將資源新增至現有的管理 OData web 服務。</span><span class="sxs-lookup"><span data-stu-id="83ef0-103">This example demonstrates how to add a resource to an existing Management OData web service by using the Management OData Schema Designer.</span></span> <span data-ttu-id="83ef0-104">[PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)範例會建立 web 服務所公開的程序和伺服器資源。</span><span class="sxs-lookup"><span data-stu-id="83ef0-104">The [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample creates a web service that exposes the Process and Server resources.</span></span> <span data-ttu-id="83ef0-105">在此範例中，您將加入至 web 服務的虛擬機器 (VM) 資源。</span><span class="sxs-lookup"><span data-stu-id="83ef0-105">In this example, you will add a Virtual Machine (VM) resource to the web service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83ef0-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="83ef0-106">Prerequisites</span></span>

<span data-ttu-id="83ef0-107">本主題假設您已下載並安裝[PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)範例中所述[建立 Windows PowerShell Web 服務](./creating-a-management-odata-web-service.md)，且您已下載並安裝[管理 OData 的結構描述設計工具](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner)。</span><span class="sxs-lookup"><span data-stu-id="83ef0-107">This topic assumes that you have downloaded and installed the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample as described in [Creating a Windows PowerShell Web Service](./creating-a-management-odata-web-service.md), and that you have downloaded and installed the [Management OData Schema Designer](https://marketplace.visualstudio.com/items?itemName=jlisc0.ManagementODataSchemaDesigner).</span></span> <span data-ttu-id="83ef0-108">本主題也假設您已設定管理 Odata 端點的電腦上安裝 HYPER-V Windows PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="83ef0-108">This topic also assumes that you have the Hyper-V Windows PowerShell module installed on the computer where you set up the Management Odata endpoint.</span></span>

## <a name="adding-vm-as-a-resource-to-the-web-service"></a><span data-ttu-id="83ef0-109">新增至 Web 服務做為資源的 VM</span><span class="sxs-lookup"><span data-stu-id="83ef0-109">Adding VM as a Resource to the Web Service</span></span>

<span data-ttu-id="83ef0-110">第一個步驟是從現有的管理 OData 端點將結構描述匯入至結構描述設計工具。</span><span class="sxs-lookup"><span data-stu-id="83ef0-110">The first step is to import the schema from the existing Management OData endpoint into the schema designer.</span></span> <span data-ttu-id="83ef0-111">下列程序描述如何執行該動作。</span><span class="sxs-lookup"><span data-stu-id="83ef0-111">The following procedure describes how to do that.</span></span>

#### <a name="importing-an-existing-schema-into-the-schema-designer"></a><span data-ttu-id="83ef0-112">現有的結構描述匯入結構描述設計工具</span><span class="sxs-lookup"><span data-stu-id="83ef0-112">Importing an existing schema into the schema designer</span></span>

1. <span data-ttu-id="83ef0-113">開啟管理 OData 的結構描述設計工具。</span><span class="sxs-lookup"><span data-stu-id="83ef0-113">Open the Management OData Schema Designer.</span></span>

2. <span data-ttu-id="83ef0-114">從**檔案**功能表上，選取**檔案**;**新**;**檔案**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-114">From the **File** menu, select **File** ; **New** ; **File**.</span></span> <span data-ttu-id="83ef0-115">**新的檔案**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="83ef0-115">The **New File** dialog appears.</span></span>

3. <span data-ttu-id="83ef0-116">按一下 **管理 OData 模型**，然後按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-116">Click **Management OData Model**, and then click **Open**.</span></span>

4. <span data-ttu-id="83ef0-117">在主視窗中，以滑鼠右鍵按一下，然後按一下 **結構描述檔案**;**匯入**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-117">Right-click in the main window, and click **Schema file** ; **Import**.</span></span> <span data-ttu-id="83ef0-118">**開啟**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="83ef0-118">The **Open** dialog appears.</span></span>

5. <span data-ttu-id="83ef0-119">瀏覽至 設定管理 OData web 服務的資料夾[PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a)範例。</span><span class="sxs-lookup"><span data-stu-id="83ef0-119">Navigate to the folder where you set up the Management OData web service for the [PswsRoleBasedPlugins](https://code.msdn.microsoft.com:443/windowsdesktop/PswsRoleBasedPlugins-9c79b75a) sample.</span></span> <span data-ttu-id="83ef0-120">如果您使用該範例使用提供的 Windows PowerShell 指令碼來設定端點，而不需要修改指令碼時，該資料夾就是**C:\inetpub\wwwroot\Modata**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-120">If you used the Windows PowerShell script provided with that sample to set up the endpoint without modifying the script, that folder is **C:\inetpub\wwwroot\Modata**.</span></span> <span data-ttu-id="83ef0-121">選取.schema.mof，然後按一下**開啟**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-121">Select Schema.mof, and click **Open**.</span></span>

   <span data-ttu-id="83ef0-122">到目前為止，在文字編輯器中，開啟的.schema.mof 和 Schema.xml 檔，並請注意，它們會包含對應的程序和服務的資源。</span><span class="sxs-lookup"><span data-stu-id="83ef0-122">At this point, open the Schema.mof and Schema.xml files in a text editor, and notice that they contain mappings for the Process and Service resources.</span></span> <span data-ttu-id="83ef0-123">Schema.mof 檔案會使用[分散式管理任務推動小組](https://www.dmtf.org/)(訊號 DTMF) 受管理物件 」 (MOF) 標準。</span><span class="sxs-lookup"><span data-stu-id="83ef0-123">The Schema.mof file uses [Distributed Management  Task Force](https://www.dmtf.org/) (DTMF) Managed Object (MOF) standard.</span></span> <span data-ttu-id="83ef0-124">Schema.xml 檔會使用 XML 結構描述中所述[資源對應的結構描述](./resource-mapping-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="83ef0-124">The schema.xml file uses an XML schema that is described in [Resource Mapping Schema](./resource-mapping-schema.md).</span></span>

   <span data-ttu-id="83ef0-125">下列程序描述如何匯入結構描述模型中的 HYPER-V cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83ef0-125">The following procedure describes how to import Hyper-V cmdlets in to the schema model.</span></span>

#### <a name="importing-cmdlets-into-the-schema"></a><span data-ttu-id="83ef0-126">Cmdlet 匯入結構描述</span><span class="sxs-lookup"><span data-stu-id="83ef0-126">Importing cmdlets into the schema</span></span>

1. <span data-ttu-id="83ef0-127">結構描述設計工具視窗的空白區域上按一下滑鼠右鍵，然後按一下 **匯入 Cmdlet**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-127">Right-click on a blank area of the schema designer window, and click **Import Cmdlets**.</span></span> <span data-ttu-id="83ef0-128">**Cmdlet 匯入精靈**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="83ef0-128">The **Cmdlet Import Wizard** dialog appears.</span></span>

2. <span data-ttu-id="83ef0-129">請確定**本機電腦**已選取，然後按一下**下一步**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-129">Make sure **Local Computer** is selected, and click **Next**.</span></span>

3. <span data-ttu-id="83ef0-130">請確定選取 已安裝 Windows PowerShell 模組，並從下拉式清單中選取 HYPER-V。</span><span class="sxs-lookup"><span data-stu-id="83ef0-130">Make sure that Installed Windows PowerShell Modules is selected, and select Hyper-V from the drop-down list.</span></span> <span data-ttu-id="83ef0-131">按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-131">click **Next**.</span></span> <span data-ttu-id="83ef0-132">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-132">Click **Next**.</span></span>

4. <span data-ttu-id="83ef0-133">在  **Cmdlet 名詞**清單中，選取**VM**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-133">In the **Cmdlet Noun** list, select **VM**.</span></span> <span data-ttu-id="83ef0-134">按 [下一步]</span><span class="sxs-lookup"><span data-stu-id="83ef0-134">Click **Next**</span></span>

5. <span data-ttu-id="83ef0-135">針對此範例中，我們會繫結只 Get 和 Delete 命令使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83ef0-135">For this example, we will bind only the Get and Delete commands with cmdlets.</span></span> <span data-ttu-id="83ef0-136">清除**建立**並**更新**核取方塊，並確定**取得**並**刪除**簽核取方塊。</span><span class="sxs-lookup"><span data-stu-id="83ef0-136">Clear the **CREATE** and **UPDATE** checkboxes, and make sure the **GET** and **DELETE** checkboxes are checked.</span></span> <span data-ttu-id="83ef0-137">請確定`Get-VM`cmdlet 會選取**取得**，而`Remove-VM`cmdlet 選取**刪除**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-137">Make sure that the `Get-VM` cmdlet is selected for **GET**, and the `Remove-VM` cmdlet is selected for **DELETE**.</span></span>

6. <span data-ttu-id="83ef0-138">因為 VM cmdlet 的中繼資料未指定輸出類型，您必須執行 cmdlet，以指定的輸出型別。</span><span class="sxs-lookup"><span data-stu-id="83ef0-138">Because the metadata for the VM cmdlets does not specify an output type, you will need to run the cmdlet to specify the output type.</span></span> <span data-ttu-id="83ef0-139">選取 **提供輸出型別**然後按一下**執行 cmdlet**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-139">Select **Provide output type** and click **Run cmdlet**.</span></span> <span data-ttu-id="83ef0-140">**執行 Cmdlet**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="83ef0-140">The **Run Cmdlet** dialog appears.</span></span> <span data-ttu-id="83ef0-141">按一下 **執行**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-141">Click **Run**.</span></span> <span data-ttu-id="83ef0-142">**CLR 型別**方塊會填入`VirtualMachine`型別。</span><span class="sxs-lookup"><span data-stu-id="83ef0-142">The **CLR Type** box is populated with the `VirtualMachine` type.</span></span> <span data-ttu-id="83ef0-143">按一下 [ **[確定]**，然後按一下**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-143">Click **OK**, then click **Next**.</span></span>

7. <span data-ttu-id="83ef0-144">根據預設，會選取所有 VirtualMachine 物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="83ef0-144">By default, all of the properties of the VirtualMachine object are selected.</span></span> <span data-ttu-id="83ef0-145">您可以清除您不想為您從 web 服務要求此資源時，傳回資料的一部分的任何屬性。</span><span class="sxs-lookup"><span data-stu-id="83ef0-145">You can clear any properties that you do not want as part of the data returned when you request this resource from the web service.</span></span> <span data-ttu-id="83ef0-146">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-146">Click **Next**.</span></span>

8. <span data-ttu-id="83ef0-147">您必須選取至少一個屬性，來做為索引鍵。</span><span class="sxs-lookup"><span data-stu-id="83ef0-147">You must select at least one property to be used as a key.</span></span> <span data-ttu-id="83ef0-148">選取 [**名稱**在清單中，按一下**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-148">Select **Name** in the list, and click **Next**.</span></span>

9. <span data-ttu-id="83ef0-149">下一步 視窗可讓您將管理 OData 資源的屬性對應到基礎的指令程式的屬性。</span><span class="sxs-lookup"><span data-stu-id="83ef0-149">The next window allows you to map properties of the Management OData resource to properties of the underlying cmdlets.</span></span> <span data-ttu-id="83ef0-150">精靈預設會對應具有相同名稱的屬性。</span><span class="sxs-lookup"><span data-stu-id="83ef0-150">The wizard maps properties with identical names by default.</span></span> <span data-ttu-id="83ef0-151">例如，`ComputerName`資源的屬性會對應至`ComputerName`指令程式的屬性。</span><span class="sxs-lookup"><span data-stu-id="83ef0-151">For example, the `ComputerName` property of the resource is mapped to the `ComputerName` property of the cmdlets.</span></span>  <span data-ttu-id="83ef0-152">這可讓您指定`ComputerName`web 服務的要求中的屬性，而且有您指定的值傳遞至`Get-VM`cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83ef0-152">This allows you to specify the `ComputerName` property in a request to the web service, and have the value you specify be passed to the `Get-VM` cmdlet.</span></span> <span data-ttu-id="83ef0-153">`Id` 和`Name`也會依預設對應。</span><span class="sxs-lookup"><span data-stu-id="83ef0-153">`Id` and `Name` are also mapped by default.</span></span>

   10. <span data-ttu-id="83ef0-154">按一下 **下一步**，然後按一下**完成**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-154">Click **Next**, then click **Finish**.</span></span>

       <span data-ttu-id="83ef0-155">在 VM 資源現在會出現在 [結構描述設計工具] 視窗中。</span><span class="sxs-lookup"><span data-stu-id="83ef0-155">The VM resource now appears in the schema designer window.</span></span> <span data-ttu-id="83ef0-156">您可以檢查的屬性和資源相關聯的作業。</span><span class="sxs-lookup"><span data-stu-id="83ef0-156">You can examine the properties and operations associated with the resource.</span></span> <span data-ttu-id="83ef0-157">接下來，您將更新的結構描述檔案匯出到 web 服務的虛擬目錄中。</span><span class="sxs-lookup"><span data-stu-id="83ef0-157">Next, you will export the updated schema files into the virtual directory for the web service.</span></span>

#### <a name="exporting-schema-files-from-the-schema-designer"></a><span data-ttu-id="83ef0-158">結構描述設計工具匯出結構描述檔案</span><span class="sxs-lookup"><span data-stu-id="83ef0-158">Exporting schema files from the schema designer</span></span>

1. <span data-ttu-id="83ef0-159">結構描述設計工具視窗的空白區域上按一下滑鼠右鍵，然後按一下 **結構描述檔案**;**匯出**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-159">Right-click on a blank area of the schema designer window, and click **Schema file** ; **Export**.</span></span> <span data-ttu-id="83ef0-160">**另存新檔**對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="83ef0-160">The **Save As** dialog appears.</span></span>

2. <span data-ttu-id="83ef0-161">從您匯入的 MOF 檔案，瀏覽至相同的目錄。</span><span class="sxs-lookup"><span data-stu-id="83ef0-161">Navigate to the same directory from where you imported the MOF file.</span></span> <span data-ttu-id="83ef0-162">檔案與原始的 MOF 檔案 (預設.schema.mof)，相同的命名，然後按一下**儲存**。</span><span class="sxs-lookup"><span data-stu-id="83ef0-162">Name the file the same as the original MOF file (Schema.mof by default), and click **Save**.</span></span> <span data-ttu-id="83ef0-163">確認您想要覆寫現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="83ef0-163">Confirm that you want to overwrite the existing file.</span></span>

   <span data-ttu-id="83ef0-164">雖然它不中明確陳述**另存新檔** 對話方塊中，這會取代.schema.mof 」 和 「 Schema.xml 檔。</span><span class="sxs-lookup"><span data-stu-id="83ef0-164">Although it is not explicitly stated in the **Save As** dialog, this replaces both the Schema.mof and Schema.xml files.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83ef0-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="83ef0-165">Next Steps</span></span>

<span data-ttu-id="83ef0-166">您可以存取新的 VM 資源從 「 管理 OData web 服務之前，您必須更新 RbacConfiguration.xml 檔案，以允許存取的 HYPER-V Windows PowerShell 模組，如中所述[設定角色為基礎的授權](./configuring-role-based-authorization.md)，而且您也必須重新啟動 web 服務。</span><span class="sxs-lookup"><span data-stu-id="83ef0-166">Before you access the new VM resource from the Management OData web service, you must update the RbacConfiguration.xml file to allow access to the Hyper-V Windows PowerShell module as described in [Configuring Role-based Authorization](./configuring-role-based-authorization.md), and you will also need to restart the web service.</span></span>