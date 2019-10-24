---
title: AccessDBProviderSample04 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a7e56-7331-4f71-9ecb-7a59b8021c68
caps.latest.revision: 10
ms.openlocfilehash: 7096f8066568c214a5902f6943a2c093932d3b56
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366337"
---
# <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

這個範例示範如何覆寫容器方法，以支援對 `Copy-Item`、`Get-ChildItem`、`New-Item` 和 @no__t 3 Cmdlet 的呼叫。 當資料存放區包含容器項目時，就應該實作這些方法。 容器是常見父項目底下的一組子項目。 這個範例中的提供者類別衍生自[ContainerCmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)類別。

## <a name="demonstrates"></a>演示

> [!IMPORTANT]
> 您的提供者類別很可能會衍生自[NavigationCmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) 。

這個範例會示範下列各項：

- 宣告 `CmdletProvider` 屬性。

- 定義一個衍生自[ContainerCmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)類別的提供者類別。

- 覆寫[ContainerCmdletProvider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem)方法，以變更 @no__t 1 Cmdlet 的行為，可讓使用者將專案從一個位置複製到另一個位置。 （此範例不會示範如何將動態參數新增至 `Copy-Item` Cmdlet）。

- 覆寫[ContainerCmdletprovider. Getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)方法，以變更 ChildItems 指令程式的行為，讓使用者能夠抓取父項目的子專案（item）。 （此範例不會示範如何將動態參數新增至 ChildItems Cmdlet）。

- 當指定 Cmdlet 的 `Name` 參數時，覆寫[ContainerCmdletprovider. Getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)方法來變更 ChildItems 指令程式的行為方式。

- 覆寫[ContainerCmdletprovider. Newitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItem)方法來變更 @no__t 1 Cmdlet 的行為，讓使用者可以將專案新增至資料存放區。 （此範例不會示範如何將動態參數新增至 `New-Item` Cmdlet）。

- 覆寫[ContainerCmdletprovider. Removeitem *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem)方法，以變更 `Remove-Item` Cmdlet 的行為。 （此範例不會示範如何將動態參數新增至 `Remove-Item` Cmdlet）。

## <a name="example"></a>範例

這個範例會示範如何覆寫複製、建立和移除專案所需的方法，以及取得父專案子專案的方法。

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a>另請參閱

[提供者： ItemCmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[提供者： ContainerCmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[提供者： NavigationCmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[設計您的 Windows PowerShell 提供者](./provider-types.md)