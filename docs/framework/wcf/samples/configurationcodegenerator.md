---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: 97197926db0b44f1ad36e2eba6ab6bec42eced33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943918"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="d5020-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="d5020-102">ConfigurationCodeGenerator</span></span>
<span data-ttu-id="d5020-103">ConfigurationCodeGenerator 是一个工具，使用该工具可以向配置系统公开您的自定义通道实现。</span><span class="sxs-lookup"><span data-stu-id="d5020-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="d5020-104">这使自定义通道的用户可以通过使用 .config 文件来配置您的通道，就像配置系统提供的绑定（如 `NetTcpBinding`）或使用 `TcpTransportBindingElement` 的自定义绑定一样。</span><span class="sxs-lookup"><span data-stu-id="d5020-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="d5020-105">当您编写自定义通道并使用新的 `BindingElement` 或 `Binding` 将其公开给编程模型时，必须创建一组类，以使 `BindingElement` 或 `Binding` 能够使用 .config 文件进行配置。</span><span class="sxs-lookup"><span data-stu-id="d5020-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="d5020-106">您可以使用 ConfigurationCodeGenerator 工具生成这些类，并改善您的客户体验。</span><span class="sxs-lookup"><span data-stu-id="d5020-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="d5020-107">生成工具</span><span class="sxs-lookup"><span data-stu-id="d5020-107">To build the tool</span></span>  
  
1. <span data-ttu-id="d5020-108">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="d5020-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="d5020-109">生成解决方案将生成一个文件：ConfigurationCodeGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="d5020-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="d5020-110">SampleRun.cmd 文件有一个演示如何使用此工具生成的类的示例命令行[传输：UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="d5020-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="d5020-111">运行此工具</span><span class="sxs-lookup"><span data-stu-id="d5020-111">To run the tool</span></span>  
  
1. <span data-ttu-id="d5020-112">如果您同时具有自定义 `BindingElement` 类型和自定义 `Binding` 类型，请在命令提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d5020-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="d5020-113">如果只有自定义 `BindingElement` 类型，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d5020-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="d5020-114">如果只有自定义 `Binding` 类型，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d5020-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="d5020-115">该命令将为 `BindingElement` 生成三个 .cs 文件（如果您指定了 /be: 选项），为标准 `Binding` 生成五个 .cs 文件（如果您指定了 /sb: 选项）以及一个 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="d5020-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1. <span data-ttu-id="d5020-116">如果您使用了 /be 选项，其中一个 .cs 文件将为您的绑定元素实现 `BindingElementExtensionSection`。</span><span class="sxs-lookup"><span data-stu-id="d5020-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="d5020-117">此代码将您的 `BindingElement` 公开给配置系统，从而使其他自定义绑定可以使用您的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="d5020-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="d5020-118">其他文件中包含代表默认值和常量的类。</span><span class="sxs-lookup"><span data-stu-id="d5020-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="d5020-119">这些文件中包含 `//TODO` 注释，用于提醒您更新默认值。</span><span class="sxs-lookup"><span data-stu-id="d5020-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2. <span data-ttu-id="d5020-120">如果你指定了 /sb 选项，两个 .cs 文件将分别实现 `StandardBindingElement` 和 `StandardBindingCollectionElement`，从而将你的标准绑定公开给配置系统。</span><span class="sxs-lookup"><span data-stu-id="d5020-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="d5020-121">其他文件中包含代表默认值和常量的类。</span><span class="sxs-lookup"><span data-stu-id="d5020-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="d5020-122">这些文件中包含 `//TODO` 注释，用于提醒您更新默认值。</span><span class="sxs-lookup"><span data-stu-id="d5020-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="d5020-123">如果指定了 /sb： 选项 CodeToAddTo\<*YourStdBinding*> 包含的代码，则必须手动添加到实现标准绑定的类。</span><span class="sxs-lookup"><span data-stu-id="d5020-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="d5020-124">必须将 SampleConfig.xml 文件中包含的配置代码添加到注册前面步骤 1 或步骤 2 中定义的处理程序的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="d5020-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
