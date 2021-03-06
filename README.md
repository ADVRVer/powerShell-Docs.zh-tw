---
ms.openlocfilehash: 0d91230aa063e58106b35a4ada1d577f316f8f27
ms.sourcegitcommit: c752ae8d0fa47eaaf3c5eae2a5a770f06c63921c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840989"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Microsoft 開放原始碼管理辦法

此專案採用了 [Microsoft 開放原始碼管理辦法](https://opensource.microsoft.com/codeofconduct/)。 如需詳細資訊，請參閱[管理辦法常見問題集 (英文)](https://opensource.microsoft.com/codeofconduct/faq/)。如果有任何其他疑問或意見，請連絡 [opencode@microsoft.com](mailto:opencode@microsoft.com)。

[即時徽章]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[預備徽章]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>組建狀態

|          即時分支          |           預備分支            |
| :---------------------------- | :---------------------------------- |
| [![即時徽章][]][即時徽章] | [![預備徽章][]][預備徽章] |

## <a name="powershell-documentation"></a>PowerShell 文件

歡迎使用裝載正式 PowerShell 文件的 PowerShell-Docs 存放庫。

## <a name="repository-structure"></a>存放庫結構

此存放庫中每個下列頂層資料夾都包含發行到 [Microsoft Docs](https://docs.microsoft.com/powershell) 的 DocSet。

- [/reference/](https://docs.microsoft.com/powershell/scripting/) 適用於 5.1、6.0 與 7.0 版的 PowerShell 概念性主題與模組參考。 此內容也是 `Get-Help` Cmdlet 擷取說明內容的來源。
  - [docs-conceptual/](https://docs.microsoft.com/powershell) - 此資料夾包含概念性文件及下列文件集：
    - [developer/](https://docs.microsoft.com/powershell/scripting/developer/) 是 PowerShell SDK 文件 (從 MSDN 移轉而來)
    - [dsc/](https://docs.microsoft.com/powershell/scripting/dsc/) 適用於 Desired State Configuration 功能
    - [gallery/](https://docs.microsoft.com/powershell/scripting/gallery) 適用於 [PowerShell 資源庫](https://www.powershellgallery.com/)
    - [jea/](https://docs.microsoft.com/powershell/scripting/learn/remoting/jea/overview) 適用於 Just Enough Administration 功能
    - [wmf/](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview) 包含 Windows Management Framework 的版本資訊。Windows Management Framework 的功能在將新版的 PowerShell 散發至舊版 Windows 的套件。

## <a name="contributing"></a>參與

我們會透過[提取要求](https://help.github.com/articles/using-pull-requests/)，主動將對此存放庫的貢獻，合併到_臨時_分支中。
請注意，提交提取要求之前，請先簽署[貢獻授權合約](https://cla.microsoft.com/)，以確保社群可以自由使用您提交的內容。

如需如何參與的詳細資訊，請閱讀我們的[參與者指南](https://docs.microsoft.com/powershell/scripting/community/contributing/overview)。
參與者指南包含有關如何參與文件、建議工具與樣式和格式需求的詳細資訊。 請使用「問題」和「提取要求」範本，以協助維持文件在不同版本之間的一致性。

## <a name="licenses"></a>授權

此專案有兩個授權檔案。 MIT 授權適用於此存放庫中包含的程式碼。 而 Creative Commons 授權則適用於文件。
