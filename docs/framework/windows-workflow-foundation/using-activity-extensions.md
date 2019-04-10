---
title: 使用活动扩展
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: e524f7e7127eb215be85b0c317474eee70830c2b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321284"
---
# <a name="using-activity-extensions"></a>使用活动扩展
活动可与工作流应用程序扩展进行交互，这些扩展允许主机提供未在工作流中显式建模的其他功能。  本主题描述如何创建和使用扩展以计算活动的执行次数。

### <a name="to-use-an-activity-extension-to-count-executions"></a>使用活动扩展来计算执行次数

1. 打开 Visual Studio 2010。 选择**新**，**项目**。 下**Visual C#** 节点中，选择**工作流**。  选择**工作流控制台应用程序**从模板列表。 将项目命名为 `Extensions`。 单击“确定”，创建项目。

2. 添加`using`的 Program.cs 文件中的语句**System.Collections.Generic**命名空间。

    ```
    using System.Collections.Generic;
    ```

3. 在 Program.cs 文件中，创建一个名为的新类**ExecutionCountExtension**。 下面的代码创建跟踪实例 Id 的工作流扩展时其**注册**调用方法。

    ```
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. 创建使用的活动**ExecutionCountExtension**。 下面的代码定义一个活动，检索**ExecutionCountExtension**对象的运行时和调用其**注册**方法执行活动时。

    ```
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. 实现中的活动**Main** program.cs 文件的方法。 以下代码包含用于生成两个不同的工作流、将每个工作流执行多次以及显示扩展中包含的结果数据的方法。

    ```
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```
