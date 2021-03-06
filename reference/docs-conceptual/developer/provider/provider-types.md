---
title: 提供者類型 |Microsoft Docs
ms.custom: ''
ms.date: 08/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523a8e1-42e4-4633-887f-fb74b3464561
caps.latest.revision: 12
ms.openlocfilehash: 0a9bfe5dd0978ffce66db1b18ef4d82be6c1a7f2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359957"
---
# <a name="provider-types"></a>提供者類型

提供者會藉由變更 PowerShell 所提供的提供者 Cmdlet 來執行其動作，藉此定義其基本功能。 例如，提供者可以使用 `Get-Item` Cmdlet 的預設功能，也可以變更從資料存放區抓取專案時該 Cmdlet 的運作方式。 本檔中所述的提供者功能包含從特定提供者基類和介面覆寫方法所定義的功能。

> [!NOTE]
> 如需 PowerShell 預先定義的提供者功能，請參閱[提供者功能](/previous-versions//ee126189(v=vs.85))。

## <a name="drive-enabled-providers"></a>啟用磁片磁碟機的提供者

啟用磁片磁碟機的提供者會指定使用者可用的預設磁片磁碟機，並允許使用者新增或移除磁片磁碟機。 在大部分情況下，提供者都是已啟用磁片磁碟機的提供者，因為它們需要一些預設磁片磁碟機來存取資料存放區。 不過，撰寫自己的提供者時，您可能會想要允許使用者建立和移除磁片磁碟機。

若要建立已啟用磁片磁碟機的提供者，您的提供者類別必須衍生自[DriveCmdletProvider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider)類別，或衍生自該類別的另一個類別。 **DriveCmdletProvider**類別會定義下列方法，以執行提供者的預設磁片磁碟機，並支援 `New-PSDrive` 和 `Remove-PSDrive` Cmdlet。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 `New-PSDrive` Cmdlet 的 `NewDrive` 方法，並選擇性地覆寫第二個方法（例如 `NewDriveDynamicParameters`），以將動態參數新增至 Cmdlet。

- [DriveCmdletProvider. InitializeDefaultDrives](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.InitializeDefaultDrives)方法會定義使用者在使用提供者時可以使用的預設磁片磁碟機。

- [DriveCmdletProvider. NewDrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive)和[DriveCmdletProvider](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters)方法會定義您的提供者如何支援 `New-PSDrive` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者建立磁片磁碟機來存取資料存放區。

- [DriveCmdletProvider. RemoveDrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive)方法會定義您的提供者支援 `Remove-PSDrive` 提供者 Cmdlet 的方式。 此 Cmdlet 可讓使用者從資料存放區移除磁片磁碟機。

## <a name="item-enabled-providers"></a>啟用專案的提供者

啟用專案的提供者可讓使用者取得、設定或清除資料存放區中的專案。 「專案」是資料存放區的元素，可供使用者獨立存取或管理。 若要建立啟用專案的提供者，您的提供者類別必須衍生自[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)類別，或衍生自該類別的另一個類別。

**ItemCmdletProvider**類別會定義用來執行特定提供者 Cmdlet 的下列方法。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 `Clear-Item` Cmdlet 的 `ClearItem` 方法，並選擇性地覆寫第二個方法（例如 `ClearItemDynamicParameters`），以將動態參數新增至 Cmdlet。

- [ItemCmdletProvider. ClearItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem)和[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters)方法會定義您的提供者如何支援 `Clear-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者移除資料存放區中某個專案的值。

- [ItemCmdletProvider. GetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem)和[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters)方法會定義您的提供者如何支援 `Get-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者從資料存放區取出資料。

- [ItemCmdletProvider. SetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem)和[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)方法會定義您的提供者如何支援 `Set-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者更新資料存放區中的專案值。

- [ItemCmdletprovider. InvokeDefaultAction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction)和[ItemCmdletprovider](/dotnet/api/system.management.automation.provider.itemcmdletprovider.invokedefaultactiondynamicparameters)方法會定義您的提供者如何支援 `Invoke-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者執行專案所指定的預設動作。

- [ItemCmdletProvider. ItemExists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists)和[ItemCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters)方法會定義您的提供者如何支援 `Test-Path` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者判斷路徑的所有元素是否都存在。

除了用來執行提供者 Cmdlet 的方法之外， **ItemCmdletProvider**類別也會定義下列方法：

- [ItemCmdletProvider. ExpandPath](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ExpandPath)方法可讓使用者在指定提供者路徑時使用萬用字元。

- [ItemCmdletProvider. IsValidPath](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.IsValidPath)是用來判斷路徑是否在語法上，以及是否對提供者而言是有效的。

## <a name="container-enabled-providers"></a>啟用容器的提供者

啟用容器的提供者可讓使用者管理容器的專案。 容器是常見父項目底下的一組子項目。 若要建立啟用容器的提供者，您的提供者類別必須衍生自[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)類別，或衍生自該類別的另一個類別。

> [!IMPORTANT]
> 啟用容器的提供者無法存取包含嵌套容器的資料存放區。 如果容器的子專案是另一個容器，您必須執行具備導覽功能的提供者。

**ContainerCmdletProvider**類別會定義用來執行特定提供者 Cmdlet 的下列方法。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 `Copy-Item` Cmdlet 的 `CopyItem` 方法，並選擇性地覆寫第二個方法（例如 `CopyItemDynamicParameters`），以將動態參數新增至 Cmdlet。

- [ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters)方法會定義您的提供者如何支援 `Copy-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者將專案從一個位置複製到另一個位置。

- [ContainerCmdletProvider. GetChildItems](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)方法會定義您的提供者如何支援 `Get-ChildItem` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者抓取父專案的子專案。

- [ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法會定義您的提供者如何支援 `Get-ChildItem` 提供者 Cmdlet （如果已指定其 `Name` 參數）的方式，則為[ContainerCmdletProvider。](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- [ContainerCmdletProvider. NewItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters)方法會定義您的提供者如何支援 `New-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者在資料存放區中建立新的專案。

- [ContainerCmdletProvider. RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters)方法會定義您的提供者如何支援 `Remove-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者從資料存放區移除專案。

- [ContainerCmdletProvider. RenameItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem)和[ContainerCmdletProvider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters)方法會定義您的提供者如何支援 `Rename-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者重新命名資料存放區中的專案。

除了用來執行提供者 Cmdlet 的方法之外， **ContainerCmdletProvider**類別也會定義下列方法：

- 提供者類別可以使用[ContainerCmdletProvider. HasChildItems](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.HasChildItems)方法，來判斷專案是否有子專案存在。

- 提供者類別可以使用[ContainerCmdletProvider. ConvertPath](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.ConvertPath)方法，從指定的路徑建立新的提供者特定路徑。

## <a name="navigation-enabled-providers"></a>具備導覽功能的提供者

啟用流覽功能的提供者可讓使用者移動資料存放區中的專案。 若要建立具備導覽功能的提供者，您的提供者類別必須衍生自[NavigationCmdletProvider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)類別。

**NavigationCmdletProvider**類別會定義用來執行特定提供者 Cmdlet 的下列方法。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 `Move-Item` Cmdlet 的 `MoveItem` 方法，並選擇性地覆寫第二個方法（例如 `MoveItemDynamicParameters`），以將動態參數新增至 Cmdlet。

- [NavigationCmdletProvider. MoveItem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem)和[NavigationCmdletProvider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)方法會定義您的提供者如何支援 `Move-Item` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者將專案從存放區中的一個位置移到另一個位置。

- [NavigationCmdletProvider. MakePath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath)方法會定義您的提供者支援 `Join-Path` 提供者 Cmdlet 的方式。 此 Cmdlet 可讓使用者結合父系和子路徑區段，以建立提供者內部路徑。

除了用來執行提供者 Cmdlet 的方法之外， **NavigationCmdletProvider**類別也會定義下列方法：

- [NavigationCmdletProvider. GetChildName](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName)方法會將路徑的子節點的名稱解壓縮出來。

- [NavigationCmdletProvider. GetParentPath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath)方法會將路徑的父系部分解壓縮出來。

- [NavigationCmdletProvider. IsItemContainer](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer)方法會判斷此專案是否為容器專案。 在此內容中，容器是通用父專案底下的子專案群組。

- [NavigationCmdletProvider. NormalizeRelativePath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath)方法會傳回相對於指定之基底路徑之專案的路徑。

## <a name="content-enabled-providers"></a>啟用內容的提供者

啟用內容的提供者可讓使用者清除、取得或設定資料存放區中的專案內容。
例如，FileSystem 提供者可讓您清除、取得及設定檔案系統中的檔案內容。 若要建立啟用內容的提供者，您的提供者類別必須執行[IContentCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider)介面的方法。

**IContentCmdletProvider**介面會定義用來執行特定提供者 Cmdlet 的下列方法。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 `Clear-Content` Cmdlet 的 `ClearContent` 方法，並選擇性地覆寫第二個方法（例如 `ClearContentDynamicParameters`），以將動態參數新增至 Cmdlet。

- [IContentCmdletProvider. ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent)和[IContentCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters)方法會定義您的提供者如何支援 `Clear-Content` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者刪除專案的內容，而不需刪除專案。

- [IContentCmdletProvider. GetContentReader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader)和[IContentCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters)方法會定義您的提供者如何支援 `Get-Content` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者取得專案的內容。 `System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader` 方法會傳回[IContentReader](/dotnet/api/System.Management.Automation.Provider.IContentReader)介面，以定義用來讀取內容的方法。

- [IContentCmdletProvider. GetContentWriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter)和[IContentCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters)方法會定義您的提供者如何支援 `Set-Content` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者更新專案的內容。 `System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter` 方法會傳回[IContentWriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter)介面，以定義用來寫入內容的方法。

## <a name="property-enabled-providers"></a>啟用屬性的提供者

啟用屬性的提供者可讓使用者管理資料存放區中專案的屬性。
若要建立已啟用屬性的提供者，您的提供者類別必須實[System.Management.Automation.Provider.IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider)和 [System.Management.Automation.Provider.IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider) 的方法，才能執行此功能。 介面。 在大部分情況下，若要支援提供者 Cmdlet，您必須覆寫 PowerShell 引擎呼叫的方法，以叫用 Cmdlet，例如 Clear-Property Cmdlet 的 `ClearProperty` 方法，並選擇性地覆寫第二個方法（例如 `ClearPropertyDynamicParameters`），以將動態參數新增至 Cmdlet。

**IPropertyCmdletProvider**介面會定義用來執行特定提供者 Cmdlet 的下列方法：

- [IPropertyCmdletProvider. ClearProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty)和[IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters)方法會定義您的提供者如何支援 `Clear-ItemProperty` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者刪除屬性的值。

- [IPropertyCmdletProvider. GetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty)和[IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters)方法會定義您的提供者如何支援 `Get-ItemProperty` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者取得專案的屬性。

- [IPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty)和[IPropertyCmdletProvider. SetPropertyDynamicParameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters)方法會定義您的提供者如何支援 `Set-ItemProperty` 提供者指令程式的方式，以及。 此 Cmdlet 可讓使用者更新專案的屬性。

  **IDynamicPropertyCmdletProvider**介面會定義用來執行特定提供者 Cmdlet 的下列方法：

- [IDynamicPropertyCmdletProvider. CopyProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters)方法會定義您的提供者如何支援 `Copy-ItemProperty` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者將屬性和其值從一個位置複製到另一個位置。

- [IDynamicPropertyCmdletProvider. MoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters)方法會定義您的提供者如何支援 `Move-ItemProperty` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者將屬性和其值從一個位置移到另一個位置。

- [IDynamicPropertyCmdletProvider. NewProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters)方法會定義您的提供者如何支援 `New-ItemProperty` 提供者指令程式的方式，而不是。 此 Cmdlet 可讓使用者建立新的屬性，並設定其值。

- [IDynamicPropertyCmdletProvider. RemoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters)方法會定義您的提供者如何支援 `Remove-ItemProperty` 指令程式的方式，也就是如此。 此 Cmdlet 可讓使用者刪除屬性及其值。

- [IDynamicPropertyCmdletProvider. RenameProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty)和[IDynamicPropertyCmdletProvider](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters)方法會定義您的提供者如何支援 `Rename-ItemProperty` 指令程式的方式，也就是如此。 此 Cmdlet 可讓使用者變更屬性的名稱。

## <a name="see-also"></a>另請參閱

[about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers)

[撰寫 Windows PowerShell 提供者](./writing-a-windows-powershell-provider.md)
