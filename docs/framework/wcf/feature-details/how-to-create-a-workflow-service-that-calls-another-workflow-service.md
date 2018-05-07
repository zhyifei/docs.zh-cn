---
title: 如何：创建可调用其他工作流服务的工作流服务
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: fda5a7286c3d20c7cdc2093e58bfe3fbdcf1d1c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a>如何：创建可调用其他工作流服务的工作流服务
有时，一个工作流服务必须从另一个工作流服务中获取信息。  本主题演示如何从一个工作流服务调用另一个工作流服务。 本主题中，我们将创建两个工作流服务：一个服务具有可反转输入字符串的方法，另一个服务在反转使用第一个服务的字符串后，将输入字符串转换为大写。  
  
### <a name="to-create-the-reverser-workflow-service"></a>创建 Reverser 工作流服务  
  
1.  以管理员身份运行 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  选择**文件**，**新项目**。 下**工作流**中的节点**已安装的模板**窗格中，选择**WCF 工作流服务应用程序**。 将解决方案命名`NestedServices`，然后单击**确定**。  
  
3.  下**服务器**，请确保**使用本地 IIS Web 服务器**选择。 单击**创建虚拟目录**。 单击**确定**对话框，其内容已成功创建虚拟目录中。  
  
4.  在解决方案资源管理器，将 Service1.xamlx 重命名为`StringReverserService.xamlx`。  
  
5.  上**项目属性**新项目页上，单击**Web**选项卡。设置**启动操作**到**特定页**，然后选择 StringReverserService.xamlx 作为启动页。  
  
6.  在设计器中打开 StringReverserService.xamlx，删除现有的 `ReceiveRequest` 和 `SendReply` 活动，然后将 `ReceiveAndSendReply` 活动拖到现有的序列活动中。  
  
    1.  设置**OperationName**为 ReverseString。  
  
    2.  设置**ServiceContractName**设置为 IReverseString。  
  
    3.  选择**CanCreateInstance**复选框。  
  
7.  选择**SequentialService**活动，然后再单击**变量**设计器底部的选项卡。 创建两个分别名为 StringToReverse 和 ReversedStringToReturn 的 String 类型的新变量。  
  
8.  单击**定义**中链接**接收**活动。 单击**参数**，并创建一个名为 InputString 的类型分配给 StringToReverse 的字符串参数。  
  
9. 单击**定义**中链接**SendReplyToReceive**活动。 单击**参数**，并创建一个名为 ReversedString 的分配给 ReversedStringToReturn 的 String 的类型参数。  
  
10. 若要实现服务的逻辑，请在名为 StringLibrary 的项目中创建一个新类。  将类定义替换为以下代码。  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. 若要对输入调用 ReverseString 方法，拖动**InvokeMethod**活动从工具箱到之间的空间**接收**和**SendReply**活动。 按如下方式设置活动的属性：  
  
    1.  **MethodName**: ReverseString  
  
    2.  **结果**: ReversedStringToReturn  
  
    3.  **参数**： 创建一个新的参数与**方向**为 In、**类型**的字符串，和一个**值**为 StringToReverse。  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. 按 F5 测试服务。 在随即出现的“WCF 测试客户端”中，双击 ReverseString() 方法。 在请求窗格中，输入`Sample`为 InputString 参数的值。 单击**调用**。 服务应返回“elpmaS”。  
  
### <a name="to-create-the-uppercaser-workflow-service"></a>创建 UpperCaser 工作流服务  
  
1.  右键单击 NestedServices 项目并选择**添加**，**新项**。 在**工作流**节点中，选择**WCF 工作流服务**，并命名为新服务`UpperCaserService`。 单击 **添加**。 此操作应将名为 UpperCaserService.xamlx 的新工作流服务添加到项目中。  
  
2.  在设计器中打开 UpperCaserService.xamlx，删除现有**ReceiveRequest**和`SendReply`活动，然后拖动`ReceiveAndSendReply`到现有的序列活动的活动。  
  
    1.  设置**OperationName**为 UpperCaseString。  
  
    2.  设置**ServiceContractName**设置为 IUpperCaseString。  
  
    3.  选择**CanCreateInstance**复选框。  
  
3.  选择 SequentialService 活动，然后单击**变量**设计器底部的选项卡。 创建三个分别名为 StringToUpper、StringToReverse 和 StringToReturn 的 String 类型的新变量。  
  
4.  单击**定义**中链接**接收**活动。 单击**参数**，并创建一个名为 InputString 的类型分配给 StringToUpper 的字符串参数。  
  
5.  单击**定义**中链接**SendReplyToReceive**活动。 单击**参数**，并创建一个名为 ModifiedString 的分配给 StringToReturn 的 String 的类型参数。  
  
6.  若要实现服务的逻辑，请使用下面的代码在 StringLibrary 类中创建一个新方法。  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  若要对输入调用 UpperCaseString 方法，拖动**InvokeMethod**活动从工具箱到之间的空间**接收**和**SendReply**活动。 按如下方式设置活动的属性：  
  
    1.  **MethodName**: UpperCaseString  
  
    2.  **结果**: StringToReverse  
  
    3.  **参数**： 创建一个新的参数与**方向**为 In、**类型**的字符串，和一个**值**为 StringToUpper。  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  现在将对已修改的字符串调用第一个服务。 右键单击项目并选择**添加服务引用**。 添加对在服务的服务引用http://localhost/NestedServices/StringReverserService.xamlx和生成项目以创建自定义活动来访问第一个 Web 服务。  
  
9. 将新活动的实例之间拖到工作流， **InvokeMethod**活动和**SendReplyToReceive**活动。 将 StringToReverse 变量分配给新活动的 InputString 属性，并将 StringToReturn 变量分配给 StringToReturn 属性。  
  
10. 打开 NestedServices 项目的属性页并更改**特定页**中**Web**为 UpperCaserService.xamlx 的选项卡。  
  
11. 按 F5 测试服务。 在随即出现的“WCF 测试客户端”中，双击 ReverseString() 方法。 在请求窗格中，输入`Sample`为 InputString 参数的值。 单击**调用**。 服务应返回“ELPMAS”。  
  
### <a name="to-create-a-client-to-call-the-services"></a>创建要调用服务的客户端  
  
1.  将一个名为 Client 的新控制台应用程序项目添加到解决方案。  
  
2.  右键单击客户端项目并选择**添加服务引用**。 在出现的窗口中，单击**发现**。 选择 StringReverserService.xamlx，并输入 ReverseService 作为命名空间。  单击 **“确定”**。  
  
3.  将 Program.cs 中 Main 方法替换为以下代码。  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
