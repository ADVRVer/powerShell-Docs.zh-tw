---
title: 使用 Windows PowerShell API 作業的排程 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64718f8e-de60-4fb7-894d-2975b5257ff6
caps.latest.revision: 4
ms.openlocfilehash: 8e1d2feff0665f169966f7d5e99540088e66bdfb
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056221"
---
# <a name="scheduling-jobs-with-the-powershell-api"></a><span data-ttu-id="dbb23-102">使用 PowerShell API 的排程工作</span><span class="sxs-lookup"><span data-stu-id="dbb23-102">Scheduling jobs with the PowerShell API</span></span>

<span data-ttu-id="dbb23-103">您可以使用所公開的物件**Microsoft.PowerShell.ScheduledJob**命名空間，以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dbb23-103">You can use the objects exposed by the **Microsoft.PowerShell.ScheduledJob** namespace to do the following:</span></span>

- <span data-ttu-id="dbb23-104">建立排程的工作。</span><span class="sxs-lookup"><span data-stu-id="dbb23-104">Create a scheduled job.</span></span>
- <span data-ttu-id="dbb23-105">定義作業執行時。</span><span class="sxs-lookup"><span data-stu-id="dbb23-105">Define when the job runs.</span></span>
- <span data-ttu-id="dbb23-106">取得有關已完成工作的結果。</span><span class="sxs-lookup"><span data-stu-id="dbb23-106">Get results about the completed job.</span></span>

## <a name="triggering-the-job"></a><span data-ttu-id="dbb23-107">觸發作業</span><span class="sxs-lookup"><span data-stu-id="dbb23-107">Triggering the job</span></span>

<span data-ttu-id="dbb23-108">建立排程的工作的第一個步驟指定應該執行的工作。</span><span class="sxs-lookup"><span data-stu-id="dbb23-108">The first step in creating a scheduled job is specifying when the job should run.</span></span> <span data-ttu-id="dbb23-109">建立並設定執行這項操作**Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger**物件。</span><span class="sxs-lookup"><span data-stu-id="dbb23-109">Do this by creating and configuring a **Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger** object.</span></span> <span data-ttu-id="dbb23-110">下列程式碼會建立排程工作來執行一次在未來的 20 秒的觸發程序。</span><span class="sxs-lookup"><span data-stu-id="dbb23-110">The following code creates a trigger that schedules a job to run a single time 20 seconds in the future.</span></span>

```csharp
ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
                    DateTime.Now.AddSeconds(20), // Create trigger to start job in 20 seconds.
                    TimeSpan.Zero,               // No random delay
                    null,                        // No repetition interval time
                    null,                        // No repetition interval duration
                    1,                           // Trigger Id
                    true);                       // Create trigger enabled

```

## <a name="defining-the-job"></a><span data-ttu-id="dbb23-111">定義作業</span><span class="sxs-lookup"><span data-stu-id="dbb23-111">Defining the job</span></span>

<span data-ttu-id="dbb23-112">您可以建立參數字典，以定義以 PowerShell 工作。</span><span class="sxs-lookup"><span data-stu-id="dbb23-112">You define a PowerShell job by creating a parameter dictionary.</span></span> <span data-ttu-id="dbb23-113">支援下列參數：</span><span class="sxs-lookup"><span data-stu-id="dbb23-113">The following parameters are supported:</span></span>

|<span data-ttu-id="dbb23-114">參數名稱</span><span class="sxs-lookup"><span data-stu-id="dbb23-114">Parameter Name</span></span>|<span data-ttu-id="dbb23-115">描述</span><span class="sxs-lookup"><span data-stu-id="dbb23-115">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="dbb23-116">**名稱**</span><span class="sxs-lookup"><span data-stu-id="dbb23-116">**Name**</span></span>|<span data-ttu-id="dbb23-117">作業名稱。</span><span class="sxs-lookup"><span data-stu-id="dbb23-117">The name of the job.</span></span>|
|<span data-ttu-id="dbb23-118">**ScriptBock**</span><span class="sxs-lookup"><span data-stu-id="dbb23-118">**ScriptBock**</span></span>|<span data-ttu-id="dbb23-119">指定作業的 PowerShell 指令碼區塊。</span><span class="sxs-lookup"><span data-stu-id="dbb23-119">A PowerShell script block that specifies what the job does.</span></span>|
|<span data-ttu-id="dbb23-120">**FilePath**</span><span class="sxs-lookup"><span data-stu-id="dbb23-120">**FilePath**</span></span>|<span data-ttu-id="dbb23-121">包含 PowerShell 指令碼區塊來指定作業的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="dbb23-121">Path to a file that contains a PowerShell script block to specify what the job does.</span></span>|
|<span data-ttu-id="dbb23-122">**InitializationScript**</span><span class="sxs-lookup"><span data-stu-id="dbb23-122">**InitializationScript**</span></span>|<span data-ttu-id="dbb23-123">PowerShell 指令碼區塊，以初始化工作。</span><span class="sxs-lookup"><span data-stu-id="dbb23-123">A PowerShell script block that initializes the job.</span></span>|
|<span data-ttu-id="dbb23-124">**ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="dbb23-124">**ArgumentList**</span></span>|<span data-ttu-id="dbb23-125">指定此作業需要的引數的物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="dbb23-125">An array of objects that specify arguments that the job takes.</span></span>|
|<span data-ttu-id="dbb23-126">**RunAs32**</span><span class="sxs-lookup"><span data-stu-id="dbb23-126">**RunAs32**</span></span>|<span data-ttu-id="dbb23-127">布林值，指定是否要以 32 位元處理序執行作業。</span><span class="sxs-lookup"><span data-stu-id="dbb23-127">A boolean value that specifies whether to run the job in a 32-bit process.</span></span>|

<span data-ttu-id="dbb23-128">下列程式碼會建立一個參數字典物件，並設定**名稱**並**ScriptBlock**參數。</span><span class="sxs-lookup"><span data-stu-id="dbb23-128">The following code creates a parameter dictionary object and sets the **Name** and **ScriptBlock** parameters.</span></span>

```csharp
string schedJobDefName = "MySampleSchedJob";
  Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
  jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

  ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
  jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath
                                                    // is required.

```

## <a name="creating-the-invocation-and-job-definition-objects"></a><span data-ttu-id="dbb23-129">建立定義物件的引動過程和工作</span><span class="sxs-lookup"><span data-stu-id="dbb23-129">Creating the invocation and job definition objects</span></span>

<span data-ttu-id="dbb23-130">接著，您建立`ScheduledJobInvocationInfo`和`ScheduledJobDefinition`物件以執行作業，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="dbb23-130">You then create `ScheduledJobInvocationInfo` and `ScheduledJobDefinition` objects to run the job as shown in the following example:</span></span>

```csharp
ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
    new JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
    jobDefParameters);

    schedJobDefinition = new ScheduledJobDefinition(
    jobInvocationInfo,                          // Defines the PowerShell job to run.
    new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the PowerShell job.
    null,                                       // No custom options. We accept default.
    null);                                      // No credentials. PowerShell job is run
                                                // in default Task Scheduler process, account.

```

## <a name="registering-the-job-with-the-task-scheduler"></a><span data-ttu-id="dbb23-131">向工作排程器作業</span><span class="sxs-lookup"><span data-stu-id="dbb23-131">Registering the job with the task scheduler</span></span>

<span data-ttu-id="dbb23-132">下列程式碼註冊的工作[Windows 工作排程器](http://go.microsoft.com/fwlink/?LinkId=251817)。</span><span class="sxs-lookup"><span data-stu-id="dbb23-132">The following code registers the job with the [Windows Task Scheduler](http://go.microsoft.com/fwlink/?LinkId=251817).</span></span>

```csharp
schedJobDefinition.Register();
    registrationSucceeded = true;
    Console.WriteLine("Scheduled job is registered. Waiting 30 seconds for it to run.");

```

## <a name="complete-code-example"></a><span data-ttu-id="dbb23-133">完整的程式碼範例</span><span class="sxs-lookup"><span data-stu-id="dbb23-133">Complete code Example</span></span>

<span data-ttu-id="dbb23-134">以下是先前的程式碼片段所採取的完整程式碼範例。</span><span class="sxs-lookup"><span data-stu-id="dbb23-134">The following is the complete code example from which the previous snippets were taken.</span></span>

```csharp
using System;
using System.Threading;
using System.Collections.Generic;
using System.Management.Automation;             // PowerShell namespace.
using Microsoft.PowerShell.ScheduledJob;        // PowerShell ScheduledJob namespace.

namespace Microsoft.Samples.PowerShell.ScheduledJob
{
    /// <summary>
    /// This class contains the Main entry point for the application.
    /// </summary>
    public class ScheduledJobSample
    {
        /// <summary>
        /// This sample shows how to use the PowerShell ScheduledJob API to create
        /// a simple PowerShell scheduled job, register it with a trigger object
        /// that defines when the job will run and retrieve job run results from
        /// the job file store.
        /// </summary>
        /// <param name="args"></param>
        public static void Main(string[] args)
        {
            // ScheduledJobDefinition contains all elements of a PowerShell scheduled
            // job including the PowerShell job script or script file path, scheduling
            // triggers, and scheduling options.
            ScheduledJobDefinition schedJobDefinition = null;
            bool registrationSucceeded = false;

            try
            {
                // First create a scheduled job trigger object.  This object will
                // define when the PowerShell job is scheduled to run.  For this
                // example we will create a trigger to run the job just one time
                // 20 seconds after the trigger object is created.
                // Note: If you are stepping through this code in a debugger you
                // may want to increase the 20 seconds value so that the trigger time
                // remains in the future once you register the scheduled job.
                ScheduledJobTrigger jobTrigger = ScheduledJobTrigger.CreateOnceTrigger(
                    DateTime.Now.AddSeconds(20),      // Create trigger to start job in 20 seconds.
                    TimeSpan.Zero,                    // No random delay
                    null,                             // No repetition interval time
                    null,                             // No repetition interval duration
                    1,                                // Trigger Id
                    true);                            // Create trigger enabled

                // Create a parameter dictionary that defines the PowerShell job.
                // For this example we will create a simple script that runs for
                // 5 seconds generating output.
                // Here are the parameters supported to define the PowerShell job.
                // Name                 - Job name string.
                // ScriptBlock          - PowerShell ScriptBlock type.
                // FilePath             - PowerShell script file path string.
                // InitializationScript - PowerShell Scriptblock type.
                // ArgumentList         - object[] type.
                // RunAs32              - Switch (boolean type).
                string schedJobDefName = "MySampleSchedJob";
                Dictionary<string, object> jobDefParameters = new Dictionary<string, object>();
                jobDefParameters.Add("Name", schedJobDefName);      // Unique name is required.

                ScriptBlock scriptBlock = ScriptBlock.Create(@"1..5 | foreach {sleep 1; ""SchedJobOutput $_""}");
                jobDefParameters.Add("ScriptBlock", scriptBlock);  // A scriptblock or script FilePath is required.

                // Now create a JobInvocation object that contains all information about the PowerShell job to run.
                ScheduledJobInvocationInfo jobInvocationInfo = new ScheduledJobInvocationInfo(
                    new JobDefinition(typeof(ScheduledJobSourceAdapter), scriptBlock.ToString(), schedJobDefName),
                    jobDefParameters);

                // Finally create the scheduled job definition object that pulls all
                // of this information together.
                schedJobDefinition = new ScheduledJobDefinition(
                   jobInvocationInfo,                          // Defines the PowerShell job to run.
                   new ScheduledJobTrigger[1] { jobTrigger },  // Defines when to run the job.
                   null,                                       // No custom options. Accept default.
                   null);                                      // No credentials. PowerShell job is
                                                               // run in default Task Scheduler
                                                               // process, account.

                // Next we register this scheduled job object with Windows Task Scheduler.
                // The Task Scheduler runs the PowerShell script based on the provided job trigger.
                schedJobDefinition.Register();
                registrationSucceeded = true;
                Console.WriteLine("Scheduled job is registered. Waiting 30 seconds for it to run.");

                // You can see this PowerShell job task registered in the Task Scheduler UI.
                // Look under path:
                // Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs

                // Wait for Task Scheduler to run the PowerShell job.
                // This should happen in 20 seconds and then the job takes about 5 seconds to run.
                // If PowerShell job task doesn't run try increasing the trigger time in the
                // ScheduledJobTrigger object.
                // You can run this task manually from the Task Scheduler UI.
                for (int count = 1; count < 31; ++count)
                {
                    Thread.Sleep(1000);
                    Console.WriteLine(count + " seconds elapsed");
                }

                Console.WriteLine();
                Console.WriteLine("Job run results.");
                Console.WriteLine();

                // Since the PowerShell job runs in a non-interactive Task Scheduler
                // process the job status and output data is written to a file based
                // job store and the directory location is the current user local app
                // data ($env:LOCALAPPDATA).
                // This job store can be accessed through the ScheduledJobSourceAdapter class.
                ScheduledJobSourceAdapter schedJobSourceAdapter = new ScheduledJobSourceAdapter();
                IList<Job2> jobRuns = schedJobSourceAdapter.GetJobs();
                foreach (var jobRun in jobRuns)
                {
                    // Check for jobs in finished state.
                    // Note that job data is not written to the job store until the job
                    // has reached a finished state.
                    JobState jobState = jobRun.JobStateInfo.State;
                    if (jobState == JobState.Completed ||
                        jobState == JobState.Stopped ||
                        jobState == JobState.Failed)
                    {
                        // Write job run finished state.
                        Console.WriteLine("Job Status: " + jobRun.JobStateInfo.State);
                        Console.WriteLine();
                        Console.WriteLine("Job Data");

                        // Write output data.
                        foreach (var item in jobRun.Output)
                        {
                            Console.WriteLine(item.ToString());
                        }

                        // Write any errors.
                        foreach (var item in jobRun.Error)
                        {
                            Console.WriteLine(item.ToString());
                        }
                    }
                }

                Console.WriteLine();
                Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
            catch (ScheduledJobException e)
            {
                Console.WriteLine("Error: " + e.Message);
            }
            finally
            {
                // Unregister this scheduled job or an error will be thrown when
                // running this sample code again (scheduled job already exists.)
                // because all registered scheduled jobs must have a unique name.
                if (registrationSucceeded)
                {
                    schedJobDefinition.Remove(true);
                }
            }
        }
    }
}

```