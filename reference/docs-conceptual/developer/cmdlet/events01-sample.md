---
title: Events01 範例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27d0ee5e-2589-4530-92ef-c09996b80994
caps.latest.revision: 10
ms.openlocfilehash: 772f73793449856651ab6b03e1ccc14faed941fc
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561442"
---
# <a name="events01-sample"></a>Events01 範例

這個範例會示範如何建立 Cmdlet，讓使用者註冊[FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)所引發的事件。
使用此 Cmdlet 時，使用者可以註冊在特定目錄下建立檔案時要執行的動作。
這個範例是衍生自[自 objecteventregistrationbase Cmdlet](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基類。

## <a name="how-to-build-the-sample-by-using-visual-studio"></a>如何使用 Visual Studio 建立範例。

1. 安裝 Windows PowerShell 2.0 SDK 之後，流覽至 Events01 資料夾。
   預設位置為 `C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\Events01`。

2. 按兩下方案（.sln）檔案的圖示。
   這會在 Microsoft Visual Studio 中開啟範例專案。

3. 在 [建置]**** 功能表中，選取 [建置方案]****。
   範例的程式庫會建立在預設 `\bin` 或 `\bin\debug` 資料夾中。

### <a name="how-to-run-the-sample"></a>如何執行範例

1. 建立下列模組資料夾：

    `[user]/documents/windowspowershell/modules/events01`

2. 將範例的程式庫檔案複製到模組資料夾。

3. 啟動 Windows PowerShell。

4. 執行下列命令，將 Cmdlet 載入 Windows PowerShell：

    ```powershell
    import-module events01
    ```

5. 使用 FileSystemEvent 指令程式註冊在臨時目錄下建立檔案時，將會寫入訊息的動作。

    ```powershell
    Register-FileSystemEvent $env:temp Created -filter "*.txt" -action { Write-Host "A file was created in the TEMP directory" }
    ```

6. 在 TEMP 目錄下建立檔案，並請注意動作會執行（顯示訊息）。

這是依照下列步驟所產生的範例輸出。

```output
Id              Name            State      HasMoreData     Location             Command
--              ----            -----      -----------     --------             -------
1               26932870-d3b... NotStarted False                                 Write-Host "A f...

```

```powershell
Set-Content $env:temp\test.txt "This is a test file"
```

```output
A file was created in the TEMP directory
```

## <a name="requirements"></a>需求

此範例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>示範

這個範例會示範下列各項。

### <a name="how-to-write-a-cmdlet-for-event-registration"></a>如何撰寫事件註冊的 Cmdlet

此 Cmdlet 衍生自[自 objecteventregistrationbase Cmdlet](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)類別，可提供 Cmdlet 通用參數的支援 `Register-*Event` 。
衍生自[自 objecteventregistrationbase Cmdlet](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)的 Cmdlet 只需要定義其特定參數，並覆寫 `GetSourceObject` 和 `GetSourceObjectEventName` 抽象方法。

## <a name="example"></a>範例

這個範例示範如何註冊[FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)所引發的事件。

```csharp
namespace Sample
{
    using System;
    using System.IO;
    using System.Management.Automation;
    using System.Management.Automation.Runspaces;
    using Microsoft.PowerShell.Commands;

    [Cmdlet(VerbsLifecycle.Register, "FileSystemEvent")]
    public class RegisterObjectEventCommand : ObjectEventRegistrationBase
    {
        /// <summary>The FileSystemWatcher that exposes the events.</summary>
        private FileSystemWatcher fileSystemWatcher = new FileSystemWatcher();

        /// <summary>Name of the event to which the cmdlet registers.</summary>
        private string eventName = null;

        /// <summary>
        /// Gets or sets the path that will be monitored by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = true, Position = 0)]
        public string Path
        {
            get
            {
                return this.fileSystemWatcher.Path;
            }

            set
            {
                this.fileSystemWatcher.Path = value;
            }
        }

        /// <summary>
        /// Gets or sets the name of the event to which the cmdlet registers.
        /// <para>
        /// Currently System.IO.FileSystemWatcher exposes 6 events: Changed, Created,
        /// Deleted, Disposed, Error, and Renamed. Check the MSDN documentation of
        /// FileSystemWatcher for details on each event.
        /// </para>
        /// </summary>
        [Parameter(Mandatory = true, Position = 1)]
        public string EventName
        {
            get
            {
                return this.eventName;
            }

            set
            {
                this.eventName = value;
            }
        }

        /// <summary>
        /// Gets or sets the filter that will be user by the FileSystemWatcher.
        /// </summary>
        [Parameter(Mandatory = false)]
        public string Filter
        {
            get
            {
                return this.fileSystemWatcher.Filter;
            }

            set
            {
                this.fileSystemWatcher.Filter = value;
            }
        }

        /// <summary>
        /// Derived classes must implement this method to return the object that generates
        /// the events to be monitored.
        /// </summary>
        /// <returns> This sample returns an instance of System.IO.FileSystemWatcher</returns>
        protected override object GetSourceObject()
        {
            return this.fileSystemWatcher;
        }

        /// <summary>
        /// Derived classes must implement this method to return the name of the event to
        /// be monitored. This event must be exposed by the input object.
        /// </summary>
        /// <returns> This sample returns the event specified by the user with the -EventName parameter.</returns>
        protected override string GetSourceObjectEventName()
        {
            return this.eventName;
        }
    }
}
```

## <a name="see-also"></a>另請參閱

[撰寫 Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md)
