---
title: "编译项目中的 XML 架构时发生错误"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords: BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07233ed1c68f85878ffdd7131f64e30e158dc350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="f6cdb-102">编译项目中的 XML 架构时发生错误</span><span class="sxs-lookup"><span data-stu-id="f6cdb-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="f6cdb-103">编译该项目中的 XML 架构时发生错误。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="f6cdb-104">因此，XML IntelliSense 不可用。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="f6cdb-105">在项目中包含的 XML 架构定义 (XSD) 架构时发生错误。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="f6cdb-106">当你添加为项目设置与现有的 XSD 架构冲突的 XSD 架构 (.xsd) 文件时，将出现此错误。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="f6cdb-107">**错误 ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="f6cdb-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6cdb-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f6cdb-108">To correct this error</span></span>  
  
-   <span data-ttu-id="f6cdb-109">双击中的警告**错误列表**窗口。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="f6cdb-110">Visual Basic 将转到 XSD 文件的警告的源中的位置。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="f6cdb-111">更正 XSD 架构中的错误。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="f6cdb-112">确保所有必需的 XSD 架构 (.xsd) 文件都包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="f6cdb-113">你可能需要单击**显示所有文件**上**项目**菜单以查看你.xsd 文件中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="f6cdb-114">右击.xsd 文件，然后单击**包括在项目**要包含在你的项目中的文件。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="f6cdb-115">如果你使用的 XML 到架构向导，从同一源推断架构不止一次可以发生此错误。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="f6cdb-116">在这种情况下，你可以从该项目中删除现有的 XSD 架构文件添加新的 XML 架构项模板，然后提供 XML 到架构向导与所有适用的 XML 源为你的项目。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="f6cdb-117">如果在 XSD 架构中不标识了任何错误，XML 编译器可能没有足够的信息来提供详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="f6cdb-118">你可以获取更详细的错误信息，如果你确保.xsd 文件的 XML 命名空间包含在你的项目匹配标识在 Visual Studio 中设置的 XML 架构的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="f6cdb-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6cdb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6cdb-119">See Also</span></span>  
 [<span data-ttu-id="f6cdb-120">“错误列表”窗口</span><span class="sxs-lookup"><span data-stu-id="f6cdb-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)  
 [<span data-ttu-id="f6cdb-121">XML</span><span class="sxs-lookup"><span data-stu-id="f6cdb-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
