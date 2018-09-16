---
title: 在 Visual Studio 中创建启用了 AJAX 的 WCF 服务和 ASP.NET 客户端
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45678277"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>如何：创建支持 AJAX 的 WCF 服务和访问该服务的 ASP.NET 客户端

本主题演示如何使用 Visual Studio 来创建启用了 AJAX 的 Windows Communication Foundation (WCF) 服务和 ASP.NET 客户端访问该服务。

## <a name="create-an-aspnet-web-app"></a>创建 ASP.NET Web 应用

1. 打开 Visual Studio。

1. 从**文件**菜单中，选择**新建** > **项目**

1. 在中**新的项目**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**ASP.NET Web 应用程序 (.NET Framework)**。

1. 将项目命名**SandwichServices**然后单击**确定**。

1. 在中**新的 ASP.NET Web 应用程序**对话框中，选择**空**，然后选择**确定**。

   ![Visual Studio 中的 ASP.NET web 应用程序类型对话框](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>添加 web 窗体

1. 右键单击 SandwichServices 项目中的**解决方案资源管理器**，然后选择**添加** > **新项**。

1. 在中**添加新项**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**Web 窗体**模板。

1. 接受默认名称 (**WebForm1**)，然后选择**添加**。

   *WebForm1.aspx*中打开**源**视图。

1. 添加以下标记内的**\<正文 >** 标记：

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>创建启用了 AJAX 的 WCF 服务

1. 右键单击 SandwichServices 项目中的**解决方案资源管理器**，然后选择**添加** > **新项**。

1. 在中**添加新项**对话框中，展开**已安装** > **Visual C#** > **Web**类别，然后选择**WCF 服务 (ajax)** 模板。

   ![在 Visual Studio 中的 WCF 服务 (ajax) 项模板](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. 将服务命名**CostService** ，然后选择**添加**。

   *CostService.svc.cs*在编辑器中打开。

1. 在服务中实现该操作。 将以下方法添加到 CostService 类，以计算量的三明治的成本：

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>配置客户端访问服务

1. 打开*WebForm1.aspx*文件，然后选择**设计**视图。

2. 从**视图**菜单中，选择**工具箱**。

3. 展开**AJAX Extensions**节点和拖放**ScriptManager**拖到窗体。

4. 回到**源**视图中，添加以下代码之间 **\<ScriptManager >** 标记，以指定 WCF 服务的路径：

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. 添加 Javascript 函数的代码`Calculate()`。 将以下代码中的放置**head** web 窗体的部分：

    ```javascript
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   此代码调用 CostService 来计算三个三明治的价格的方法，并在调用的范围显示结果**additionResult**。

## <a name="run-the-program"></a>运行程序

请确保*WebForm1.aspx*具有焦点，，然后按**启动**按钮以启动 web 客户端。 按钮有一个绿色三角形和内容类似于**IIS Express (Microsoft Edge)**。 或者，可以按**F5**。 单击**3 三明治的价格**按钮以生成预期的输出为"3.75"。

## <a name="example-code"></a>示例代码

以下是中的完整代码*CostService.svc.cs*文件：

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

下面是完整的内容*WebForm1.aspx*页：

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
