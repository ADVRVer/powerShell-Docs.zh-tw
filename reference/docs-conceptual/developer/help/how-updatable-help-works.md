---
title: 可更新的說明如何運作
ms.date: 09/13/2016
ms.openlocfilehash: 4849ce81e31171c6822a9078a77ebb45729185a3
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893283"
---
# <a name="how-updatable-help-works"></a>可更新的說明如何運作

本主題說明「可更新的協助」如何處理每個模組的 HelpInfo XML 檔案和封包檔，並為使用者安裝更新的說明。

## <a name="the-update-help-process"></a>Update-Help 程式

下列清單說明當使用者執行命令來更新特定 UI 文化特性中模組的說明檔時， [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet 的動作。

1. `Update-Help`從模組資訊清單中的**HelpInfoURI**索引鍵值所指定的位置取得遠端 HelpInfo XML 檔案，並根據架構來驗證檔案。 （若要查看架構，請參閱[HELPINFO XML 架構](./helpinfo-xml-schema.md)）。然後 `Update-Help` 在使用者電腦上的模組目錄中尋找模組的本機 HELPINFO XML 檔案。

1. `Update-Help`比較模組的遠端和本機 HelpInfo XML 檔案中指定的 UI 文化特性之說明檔的版本號碼。 如果遠端檔案上的版本號碼大於本機檔案上的版本號碼，或如果沒有模組的本機 HelpInfo XML 檔案，則準備下載新的說明檔 `Update-Help` 。

1. `Update-Help`從遠端 HelpInfo XML 檔案中的**HelpContentUri**元素所指定的位置，選取模組的 CAB 檔案。 它會使用模組名稱、模組 GUID 和 UI 文化特性來識別 CAB 檔案。

1. `Update-Help`下載封包檔、解壓縮它、驗證說明內容檔案，並將說明內容檔案儲存在使用者電腦上模組目錄的特定語言子目錄中。

1. `Update-Help`藉由複製遠端 HelpInfo XML 檔案來建立本機 HelpInfo XML 檔案。 它會編輯本機 HelpInfo XML 檔案，使其只包含其所安裝之 CAB 檔案的元素。
   然後，它會將本機 HelpInfo XML 檔案儲存在模組目錄中，並結束更新。

## <a name="the-save-help-process"></a>儲存輔助程式

下列清單說明當使用者執行命令來更新檔案共用中的說明檔，然後使用這些檔案來更新使用者電腦上的說明檔時， [Save Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)和[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlet 的動作。

此 `Save-Help` Cmdlet 會執行下列動作，以回應命令，將模組的說明檔儲存在**DestinationPath**參數所指定的檔案共用中。

1. `Save-Help`從模組資訊清單中的**HelpInfoURI**索引鍵值所指定的位置取得遠端 HelpInfo XML 檔案，並根據架構來驗證檔案。 （若要查看架構，請參閱[HELPINFO XML 架構](./helpinfo-xml-schema.md)）。然後在 `Save-Help` 命令中的**DestinationPath**參數所指定的目錄中尋找本機 HelpInfo XML 檔案 `Save-Help` 。

1. `Save-Help`比較模組的遠端和本機 HelpInfo XML 檔案中指定的 UI 文化特性之說明檔的版本號碼。 如果遠端檔案上的版本號碼大於本機檔案上的版本號碼，或如果**DestinationPath**目錄中沒有適用于此模組的本機 HelpInfo XML 檔案，則 `Save-Help` 準備下載新的說明檔。

1. `Save-Help`從遠端 HelpInfo XML 檔案中的**HelpContentUri**元素所指定的位置，選取模組的 CAB 檔案。 它會使用模組名稱、模組 GUID 和 UI 文化特性來識別 CAB 檔案。

1. `Save-Help`下載封包檔，並將它儲存在**DestinationPath**目錄中。 （它不會建立任何語言特定的子目錄）。

1. `Save-Help`藉由複製遠端 HelpInfo XML 檔案來建立本機 HelpInfo XML 檔案。 它會編輯本機 HelpInfo XML 檔案，使其只包含所儲存之 CAB 檔案的元素。
   然後，它會將本機 HelpInfo XML 檔案儲存在**DestinationPath**目錄中，並結束更新。

   此 `Update-Help` Cmdlet 會執行下列動作，以回應命令，從**SourcePath**參數所指定之檔案共用中的檔案更新使用者電腦上的說明檔。

1. `Update-Help`從**SourcePath**目錄取得遠端 HelpInfo XML 檔案。 然後它會在使用者電腦上的模組目錄中尋找本機 HelpInfo XML 檔案。

1. `Update-Help`比較模組的遠端和本機 HelpInfo XML 檔案中指定的 UI 文化特性之說明檔的版本號碼。 如果遠端檔案上的版本號碼大於本機檔案上的版本號碼，或如果沒有本機 HelpInfo XML 檔案，則 `Update-Help` 準備安裝新的說明檔。

1. `Update-Help`從**SourcePath**目錄選取模組的 CAB 檔案。 它會使用模組名稱、模組 GUID 和 UI 文化特性來識別 CAB 檔案。

1. `Update-Help`解壓縮封包檔、驗證說明內容檔案，並將說明內容檔案儲存在使用者電腦上模組目錄的特定語言子目錄中。

1. `Update-Help`藉由複製遠端 HelpInfo XML 檔案來建立本機 HelpInfo XML 檔案。 它會編輯本機 HelpInfo XML 檔案，使其只包含其所安裝之 CAB 檔案的元素。
   然後，它會將本機 HelpInfo XML 檔案儲存在模組目錄中，並結束更新。
