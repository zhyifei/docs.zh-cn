---
title: "SchemaImporterExtension 技术示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68e89053d1d4a36a0f015ed4e0082ae88e1de6a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="33544-102">SchemaImporterExtension 技术示例</span><span class="sxs-lookup"><span data-stu-id="33544-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="33544-103">下载示例</span><span class="sxs-lookup"><span data-stu-id="33544-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="33544-104">此示例演示自定义 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>，通过它，可以在导入 XML 架构时对代码生成进行精细控制。</span><span class="sxs-lookup"><span data-stu-id="33544-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="33544-105">该应用程序演示如何生成、注册和调用此扩展。</span><span class="sxs-lookup"><span data-stu-id="33544-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="33544-106">使用命令提示生成示例</span><span class="sxs-lookup"><span data-stu-id="33544-106">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="33544-107">打开命令提示窗口，然后定位到该示例的语言特定子目录之一。</span><span class="sxs-lookup"><span data-stu-id="33544-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="33544-108">在命令行中键入“msbuild.exe OrderSchemaImporterExtension.sln”。</span><span class="sxs-lookup"><span data-stu-id="33544-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="33544-109">使用 Visual Studio 生成示例</span><span class="sxs-lookup"><span data-stu-id="33544-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="33544-110">打开[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]，定位到该示例的特定语言的子目录。</span><span class="sxs-lookup"><span data-stu-id="33544-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="33544-111">双击 OrderSchemaImporterExtension.sln 的图标，在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="33544-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="33544-112">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="33544-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="33544-113">应用程序将在默认的 \bin 或 \bin\Debug 目录中生成。</span><span class="sxs-lookup"><span data-stu-id="33544-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="33544-114">运行示例</span><span class="sxs-lookup"><span data-stu-id="33544-114">To run the sample</span></span>  
  
1.  <span data-ttu-id="33544-115">使用命令提示定位到包含新的可执行文件的目录。</span><span class="sxs-lookup"><span data-stu-id="33544-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="33544-116">在命令行中键入“[exe name]”。</span><span class="sxs-lookup"><span data-stu-id="33544-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33544-117">备注</span><span class="sxs-lookup"><span data-stu-id="33544-117">Remarks</span></span>  
 <span data-ttu-id="33544-118">有关二进制创建和注册步骤示例的更多信息，请参见源代码中的注释以及 build.proj 文件。</span><span class="sxs-lookup"><span data-stu-id="33544-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33544-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33544-119">See Also</span></span>  
 <xref:System.CodeDom.CodeCompileUnit>  
 <xref:System.CodeDom.CodeNamespace>  
 <xref:System.CodeDom.CodeNamespaceImport>  
 <xref:Microsoft.CSharp.CSharpCodeProvider>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 <xref:System.Web.Services.Description>  
 <xref:System.Web.Services.Discovery>  
 <xref:System.Xml.Serialization>  
 <xref:System.Uri>  
 <xref:Microsoft.VisualBasic.VBCodeProvider>  
 <xref:System.Web.Services.Description.WebReference>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>
