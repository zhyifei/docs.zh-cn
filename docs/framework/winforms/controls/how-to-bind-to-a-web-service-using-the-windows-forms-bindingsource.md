---
title: "如何：使用 Windows 窗体 BindingSource 绑定到 Web 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Web services [Windows Forms], binding controls
- BindingSource component [Windows Forms], binding to a Web service
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to Web service
- BindingSource component [Windows Forms], examples
ms.assetid: ee261207-4573-4cb9-a8cb-5185037e0fba
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a647f688f0ae8566a7129982e78e3d9503bee6af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource"></a><span data-ttu-id="a0a68-102">如何：使用 Windows 窗体 BindingSource 绑定到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="a0a68-102">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>
<span data-ttu-id="a0a68-103">如果想要将 Windows 窗体控件绑定到因调用 XML Web 服务获取的结果，可使用 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="a0a68-103">If you want to bind a Windows Form control to the results obtained from calling an XML Web service, you can use a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="a0a68-104">此过程类似于将 <xref:System.Windows.Forms.BindingSource> 组件绑定到类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-104">This procedure is similar to binding a <xref:System.Windows.Forms.BindingSource> component to a type.</span></span> <span data-ttu-id="a0a68-105">必须创建客户端代理，其中包含 Web 服务公开的方法和类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-105">You must create a client-side proxy that contains the methods and types exposed by the Web service.</span></span> <span data-ttu-id="a0a68-106">从 Web 服务 (.asmx) 本身或其 Web 服务描述语言 (WSDL) 文件生成客户端代理。</span><span class="sxs-lookup"><span data-stu-id="a0a68-106">You generate a client-side proxy from the Web service (.asmx) itself, or its Web Services Description Language (WSDL) file.</span></span> <span data-ttu-id="a0a68-107">此外，客户端代理必须公开 Web 服务用作公共属性的复杂类型字段。</span><span class="sxs-lookup"><span data-stu-id="a0a68-107">Additionally, your client-side proxy must expose the fields of complex types used by the Web service as public properties.</span></span> <span data-ttu-id="a0a68-108">然后将 <xref:System.Windows.Forms.BindingSource> 绑定到 Web 服务代理中公开的某个类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-108">You then bind the <xref:System.Windows.Forms.BindingSource> to one of the types exposed in the Web service proxy.</span></span>  
  
### <a name="to-create-and-bind-to-a-client-side-proxy"></a><span data-ttu-id="a0a68-109">若要创建并绑定到客户端代理</span><span class="sxs-lookup"><span data-stu-id="a0a68-109">To create and bind to a client-side proxy</span></span>  
  
1.  <span data-ttu-id="a0a68-110">在所选目录中创建 Windows 窗体，同时创建适当的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a0a68-110">Create a Windows Form in the directory of your choice, with an appropriate namespace.</span></span>  
  
2.  <span data-ttu-id="a0a68-111">将 <xref:System.Windows.Forms.BindingSource> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="a0a68-111">Add a <xref:System.Windows.Forms.BindingSource> component to the form.</span></span>  
  
3.  <span data-ttu-id="a0a68-112">打开 [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] 命令提示符，并导航到与你的窗体位置相同的目录。</span><span class="sxs-lookup"><span data-stu-id="a0a68-112">Open the [!INCLUDE[winsdklong](../../../../includes/winsdklong-md.md)] command prompt, and navigate to the same directory that your form is located in.</span></span>  
  
4.  <span data-ttu-id="a0a68-113">使用 WSDL 工具输入 Web 服务的 .asmx 文件或 WSDL 文件的 `wsdl` 和 URL，后接应用程序的命名空间，并可选择性地接正在使用的语言。</span><span class="sxs-lookup"><span data-stu-id="a0a68-113">Using the WSDL tool, enter `wsdl` and the URL for the .asmx or WSDL file for the Web service, followed by the namespace of your application, and optionally the language you are working in.</span></span>  
  
     <span data-ttu-id="a0a68-114">以下代码示例使用 Web 服务，它位于 http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx。</span><span class="sxs-lookup"><span data-stu-id="a0a68-114">The following code example uses the Web service located at http://webservices.eraserver.net/zipcoderesolver/zipcoderesolver.asmx.</span></span> <span data-ttu-id="a0a68-115">例如，对于 C# 类型，位于 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`，对于 Visual Basic 类型，则位于 `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`。</span><span class="sxs-lookup"><span data-stu-id="a0a68-115">For example, for C# type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService`, or for Visual Basic type `wsdl http://webservices.eraserver.net.zipcoderesolver/zipcoderesolver.asmx /n:BindToWebService /language:VB`.</span></span> <span data-ttu-id="a0a68-116">将路径作为参数传递到 WSDL 工具将以指定语言在与应用程序相同的目录和命名空间中生成客户端代理。</span><span class="sxs-lookup"><span data-stu-id="a0a68-116">Passing the path as an argument to the WSDL tool will generate a client-side proxy in the same directory and namespace as your application, in the specified language.</span></span> <span data-ttu-id="a0a68-117">如果正在使用 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，则将文件添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a0a68-117">If you are using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], add the file to your project.</span></span>  
  
5.  <span data-ttu-id="a0a68-118">选择客户端代理中要将绑定到的类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-118">Select a type in the client-side proxy to bind to.</span></span>  
  
     <span data-ttu-id="a0a68-119">这通常是由 Web 服务提供的方法返回的类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-119">This is typically a type returned by a method offered by the Web service.</span></span> <span data-ttu-id="a0a68-120">出于绑定目的，所选类型的字段必须公开为公共属性。</span><span class="sxs-lookup"><span data-stu-id="a0a68-120">The fields of the chosen type must be exposed as public properties for binding purposes.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#4)]  
  
6.  <span data-ttu-id="a0a68-121">将 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 属性设置为包含在 Web 服务客户端代理中的所需类型。</span><span class="sxs-lookup"><span data-stu-id="a0a68-121">Set the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property of the <xref:System.Windows.Forms.BindingSource> to the type you want that is contained in the Web service client-side proxy.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#2)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#2)]  
  
### <a name="to-bind-controls-to-the-bindingsource-that-is-bound-to-a-web-service"></a><span data-ttu-id="a0a68-122">若要将控件绑定到 BindingSource（已绑定到 Web 服务）</span><span class="sxs-lookup"><span data-stu-id="a0a68-122">To bind controls to the BindingSource that is bound to a Web service</span></span>  
  
-   <span data-ttu-id="a0a68-123">将控件绑定到 <xref:System.Windows.Forms.BindingSource>，将 Web 服务类型中的所需的公共属性作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="a0a68-123">Bind controls to the <xref:System.Windows.Forms.BindingSource>, passing the public property of the Web service type that you want as a parameter.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#3)]
     [!code-csharp[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.DataConnectorWebService#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a0a68-124">示例</span><span class="sxs-lookup"><span data-stu-id="a0a68-124">Example</span></span>  
 <span data-ttu-id="a0a68-125">以下代码示例演示了如何将 <xref:System.Windows.Forms.BindingSource> 组件绑定到 Web 服务，然后如何将文本框绑定到 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="a0a68-125">The following code example demonstrates how to bind a <xref:System.Windows.Forms.BindingSource> component to a Web service, and then how to bind a text box to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="a0a68-126">单击按钮后，将调用 Web 服务方法且结果将显示在 `textbox1` 中。</span><span class="sxs-lookup"><span data-stu-id="a0a68-126">When you click the button, a Web service method is called and the results will appear in `textbox1`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorWebService#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorWebService/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0a68-127">编译代码</span><span class="sxs-lookup"><span data-stu-id="a0a68-127">Compiling the Code</span></span>  
 <span data-ttu-id="a0a68-128">这是完整的示例，其中包括 `Main` 方法和客户端代理代码的缩写版本。</span><span class="sxs-lookup"><span data-stu-id="a0a68-128">This is a complete example that includes a `Main` method, and a shortened version of client-side proxy code.</span></span>  
  
 <span data-ttu-id="a0a68-129">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="a0a68-129">This example requires:</span></span>  
  
-   <span data-ttu-id="a0a68-130">对 System, System.Drawing、System.Web.Services、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a0a68-130">References to the System, System.Drawing, System.Web.Services, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="a0a68-131">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a68-131">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a0a68-132">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="a0a68-132">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="a0a68-133">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="a0a68-133">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a68-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0a68-134">See Also</span></span>  
 [<span data-ttu-id="a0a68-135">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="a0a68-135">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="a0a68-136">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="a0a68-136">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
