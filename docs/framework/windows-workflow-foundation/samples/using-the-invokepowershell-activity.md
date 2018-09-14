---
title: 使用 InvokePowerShell 活动
ms.date: 03/30/2017
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
ms.openlocfilehash: fa42cddd930b755e9938a02a137ee77ee273fad0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45595274"
---
# <a name="using-the-invokepowershell-activity"></a>使用 InvokePowerShell 活动
InvokePowerShell 示例演示如何使用 `InvokePowerShell` 活动调用 Windows PowerShell 命令。  
  
## <a name="demonstrates"></a>演示  
  
-   Windows PowerShell 命令的简单创新。  
  
-   从 Windows PowerShell 输出管道检索值，并将这些值存储在工作流变量中。  
  
-   将数据作为执行命令的输入管道传入 Windows PowerShell 中。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a>讨论  
 此示例包含以下三个项目。  
  
|项目名称|描述|主要文件|  
|------------------|-----------------|----------------|  
|CodedClient|使用 PowerShell 活动的示例客户端应用程序。|-   **Program.cs**： 以编程方式创建调用 InvokePowerShell 活动的基于序列的工作流。|  
|DesignerClient|一个自定义活动集，其中包含 `InvokePowerShell` 自定义活动、其他杂项自定义活动和一个使用这些活动的工作流。|<ul><li>活动：<br /><br /> <ul><li>**PrintCollection.cs**： 打印到控制台集合中的所有项的帮助器活动。</li><li>**ReadLine.cs**： 从控制台读取输入的帮助器活动。</li></ul></li><li>文件系统：<br /><br /> <ul><li>**Copy.xaml**： 将文件复制的活动。</li><li>**CreateFile.xaml**： 创建一个文件的活动。</li><li>**DeleteFile.xaml**： 删除的文件的活动。</li><li>**MakeDir.xaml**： 创建目录的活动。</li><li>**Move.xaml**： 将文件移动的活动。</li><li>**ReadFile.xaml**： 读取文件，并返回其内容的活动。</li><li>**TestPath.xaml**： 一个测试路径是否存在的活动。</li></ul></li><li>进程：<br /><br /> <ul><li>**GetProcess.xaml**： 获取正在运行的进程列表的活动。</li><li>**StopProcess.xaml**： 停止特定进程的活动。</li></ul></li><li>**Program.cs**： 调用 Sequence1 工作流。</li><li>**Sequence1.xaml**： 基于序列的工作流。</li></ul>|  
|PowerShell|`InvokePowerShell` 活动及其关联的设计器。|活动文件<br /><br /> -   **ExecutePowerShell.cs**: 活动的主执行逻辑。<br />-   **InvokePowerShell.cs**： 包含泛型 （返回值） 版本和非泛型 （非返回值） 版本的主执行逻辑周围的包装。 这是活动的公共接口。<br />-   **NoPersistZone.cs**： 此活动可防止任何子活动持久化。 在 `InvokePowerShell` 活动实现中使用该类以防止在执行期间将活动持久化。<br /><br /> 设计器文件：<br /><br /> 1.**ArgumentDictionaryEditor.cs**： 允许用户编辑的参数的 Windows 对话框`InvokePowerShell`活动。<br />2.**GenericInvokePowerShellDesigner.xaml**并**GenericInvokePowerShellDesigner.xaml.cs**： 定义的泛型外观`InvokePowerShell`中的活动[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]。<br />3.**InvokePowerShellDesigner.xaml**并**InvokePowerShellDesigner.cs**： 定义的非泛型外观`InvokePowerShell`中的活动[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]。|  
  
 首先讨论客户端项目，因为在了解 PowerShell 活动的用法之后再了解它的内部功能会更容易一些。  
  
## <a name="using-this-sample"></a>使用此示例  
 以下各节说明如何使用此示例中的三个项目。  
  
### <a name="using-the-coded-client-project"></a>使用 CodedClient 项目  
 示例客户端以编程方式创建一个顺序活动，其中包含几个使用 `InvokePowerShell` 活动的不同的方法的示例。 第一次调用将启动“记事本”。  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 第二次调用将获取本地计算机上正在运行的进程的列表。  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 `Output` 是用于存储命令输出的变量。  
  
 下一次调用将演示如何对 PowerShell 调用的每个单独输出运行后续处理步骤。 `InitializationAction` 将设置为输出每个进程的字符串表示形式的函数。 `Output` 活动将在 `InvokePowerShell<string>` 变量中返回这些字符串的集合。  
  
 后续的 `InvokePowerShell` 调用演示如何将数据传入到活动中以及如何显示输出和错误。  
  
### <a name="using-the-designer-client-project"></a>使用 DesignerClient 项目  
 DesignerClient 项目由一组自定义活动组成，生成的所有这些活动几乎都包含 `InvokePowerShell` 活动。 大多数活动都调用非泛型版本的 `InvokePowerShell` 活动，并且不期待返回值。 其他活动使用泛型版本的 `InvokePowerShell` 活动，并使用 `InitializationAction` 参数对结果进行后续处理。  
  
## <a name="using-the-powershell-project"></a>使用 PowerShell 项目  
 活动的主要操作是在 `ExecutePowerShell` 类中进行的。 由于执行 PowerShell 命令时将不会阻止主要工作流线程，因此通过从 <xref:System.Activities.AsyncCodeActivity> 类继承可将活动创建为异步活动。  
  
 工作流运行时调用 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 方法以开始运行活动。 首先，它通过调用 PowerShell API 来创建 PowerShell 管道。  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 然后，它创建一个 PowerShell 命令并在此命令中填入参数和变量。  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 此时，已传入的输入也将发送到此管道。 最后，此管道将包装在 `PipelineInvokerAsyncResult` 对象中，并会返回此管道。 `PipelineInvokerAsyncResult` 对象注册侦听器并调用此管道。  
  
```  
pipeline.InvokeAsync();  
```  
  
 在完成执行后，输出和错误将存储在同一个 `PipelineInvokerAsyncResult` 对象中，并会通过调用最初传递到 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 的回调方法将控制交还给工作流运行时。  
  
 在方法的执行过程结束时，工作流运行时会调用活动的 <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> 方法。  
  
 `InvokePowerShell` 类包装 `ExecutePowerShellCommand` 类并创建活动的两个版本，即泛型版本和非泛型版本。 非泛型版本直接返回 PowerShell 执行的输出，而泛型版本会将各个结果转换为泛型类型。  
  
 将泛型版本的活动作为一个顺序工作流实现，这将调用 `ExecutePowerShellCommand` 并对其结果进行后续处理。 对于结果集合中的每个元素，后续处理步骤将调用 `InitializationAction`（如果已设置的话）。 否则，它将执行一个简单的强制转换。  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 已为两个 `InvokePowerShell` 活动（泛型和非泛型）创建了设计器。 InvokePowerShellDesigner.xaml 及其关联的 .cs 文件定义非泛型版本的 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 活动在 `InvokePowerShell` 中时的外观。 在 InvokePowerShellDesigner.xaml 中，将使用 <xref:System.Windows.Controls.DockPanel> 表示图形界面。  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 请注意，文本框的 `Text` 属性是一个双向绑定，它可确保活动的 `CommandText` 属性的值与设计器中输入的值相等。  
  
 GenericInvokePowerShellDesigner.xaml 及其关联的 .cs 文件定义了泛型 `InvokePowerShell` 活动的图形界面。 设计器会稍微复杂一些，因为它允许用户设置 `InitializationAction`。 关键在于使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 以允许将子活动拖放到 `InvokePowerShell` 设计器图面上。  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 设计器自定义并不仅限于用于定义活动在设计画布上的外观的 .xaml 文件。 还可以自定义用于显示活动参数的对话框。 这些参数和 PowerShell 变量将影响 PowerShell 命令的行为。 该活动将其作为公开<!--zz <xref:System.Collections.Generic.Dictionary%601>-->`System.Collections.Generic.Dictionary`类型。 ArgumentDictionaryEditor.cs、PropertyEditorResources.xaml 和 PropertyEditorResources.cs 定义可供你用来编辑这些类型的对话框。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
 必须安装 Windows PowerShell 才能运行此示例。 可以从以下位置安装 Windows PowerShell: [Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=150383)。  
  
#### <a name="to-run-the-coded-client"></a>运行 CodedClient  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 PowerShell.sln。  
  
2.  右击该解决方案并生成它。  
  
3.  右键单击**CodedClient**项目，然后选择**设为启动项目**。  
  
4.  按 Ctrl+F5 运行应用程序。  
  
#### <a name="to-run-the-designer-client"></a>运行 DesignerClient  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 PowerShell.sln。  
  
2.  右击该解决方案并生成它。  
  
3.  右键单击**DesignerClient**项目，然后选择**设为启动项目**。  
  
4.  按 Ctrl+F5 运行应用程序。  
  
## <a name="known-issues"></a>已知问题  
  
1.  如果从另一个项目引用 `InvokePowerShell` 活动程序集或项目时导致出现生成错误，则可能需要手动将 `<SpecificVersion>True</SpecificVersion>` 元素添加到该新项目的 .csproj 文件中引用 `InvokePowerShell` 的行下方。  
  
2.  如果未安装 Windows PowerShell，只要您将添加在 Visual Studio 中显示以下错误消息`InvokePowerShell`到工作流活动： `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`  
  
3.  在 Windows PowerShell 2.0 中，以编程方式调用 `$input.MoveNext()` 失败，并且使用 `$input.MoveNext()` 的脚本会产生意外的错误和结果。 若要解决此问题，请考虑在循环访问数组时使用 PowerShell 谓词 `foreach` 而不是调用 `MoveNext()`。    
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`