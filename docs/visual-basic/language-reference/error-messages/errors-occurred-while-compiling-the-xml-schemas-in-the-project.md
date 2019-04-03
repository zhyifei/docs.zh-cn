---
title: 编译项目中的 XML 架构时发生错误
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 337fc1fb4dfc83c9b4814d3e45eb0cbe0758f7ce
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842520"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a><span data-ttu-id="64acf-102">编译项目中的 XML 架构时发生错误</span><span class="sxs-lookup"><span data-stu-id="64acf-102">Errors occurred while compiling the XML schemas in the project</span></span>
<span data-ttu-id="64acf-103">编译项目中的 XML 架构时发生错误。</span><span class="sxs-lookup"><span data-stu-id="64acf-103">Errors occurred while compiling the XML schemas in the project.</span></span> <span data-ttu-id="64acf-104">因此，XML IntelliSense 不可用。</span><span class="sxs-lookup"><span data-stu-id="64acf-104">Because of this, XML IntelliSense is not available.</span></span>  
  
 <span data-ttu-id="64acf-105">在项目中包含的 XML 架构定义 (XSD) 架构中没有错误。</span><span class="sxs-lookup"><span data-stu-id="64acf-105">There is an error in an XML Schema Definition (XSD) schema included in the project.</span></span> <span data-ttu-id="64acf-106">添加与现有的 XSD 架构冲突设置项目的 XSD 架构 (.xsd) 文件时，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="64acf-106">This error occurs when you add an XSD schema (.xsd) file that conflicts with the existing XSD schema set for the project.</span></span>  
  
 <span data-ttu-id="64acf-107">**错误 ID:** BC36810</span><span class="sxs-lookup"><span data-stu-id="64acf-107">**Error ID:** BC36810</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64acf-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="64acf-108">To correct this error</span></span>  
  
-   <span data-ttu-id="64acf-109">双击中的警告**错误列表**窗口。</span><span class="sxs-lookup"><span data-stu-id="64acf-109">Double-click the warning in the **Errors List** window.</span></span> <span data-ttu-id="64acf-110">Visual Basic 将转到源的警告的 XSD 文件中的位置。</span><span class="sxs-lookup"><span data-stu-id="64acf-110">Visual Basic will take you to the location in the XSD file that is the source of the warning.</span></span> <span data-ttu-id="64acf-111">更正的 XSD 架构中的错误。</span><span class="sxs-lookup"><span data-stu-id="64acf-111">Correct the error in the XSD schema.</span></span>  
  
-   <span data-ttu-id="64acf-112">请确保所有必需的 XSD 架构 (.xsd) 文件都包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="64acf-112">Ensure that all required XSD schema (.xsd) files are included in the project.</span></span> <span data-ttu-id="64acf-113">可能需要单击**显示所有文件**上**项目**中的下拉菜单，看看您.xsd 文件**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="64acf-113">You may need to click **Show All Files** on the **Project** menu to see your .xsd files in **Solution Explorer**.</span></span> <span data-ttu-id="64acf-114">右键单击一个.xsd 文件，然后单击**包括在项目**将该文件包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="64acf-114">Right-click an .xsd file and then click **Include In Project** to include the file in your project.</span></span>  
  
-   <span data-ttu-id="64acf-115">如果使用 XML 到架构向导时，如果从同一源推断架构不止一次可以发生此错误。</span><span class="sxs-lookup"><span data-stu-id="64acf-115">If you are using the XML to Schema Wizard, this error can occur if you infer schemas more than one time from the same source.</span></span> <span data-ttu-id="64acf-116">在这种情况下，您可以从项目中，删除现有的 XSD 架构文件将添加新的 XML 到架构项模板，然后提供 XML 到架构向导使用所有适用的 XML 源为您的项目。</span><span class="sxs-lookup"><span data-stu-id="64acf-116">In this case, you can remove the existing XSD schema files from the project, add a new XML to Schema item template, and then provide the XML to Schema Wizard with all the applicable XML sources for your project.</span></span>  
  
-   <span data-ttu-id="64acf-117">如果在 XSD 架构中不标识任何错误，则 XML 编译器可能没有足够的信息来提供详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="64acf-117">If no error is identified in your XSD schema, the XML compiler may not have enough information to provide a detailed error message.</span></span> <span data-ttu-id="64acf-118">你可以获取更详细的错误信息，如果您确保.xsd 文件的 XML 命名空间包含的项目匹配项标识为 Visual Studio 中设置 XML 架构的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="64acf-118">You may be able to get more detailed error information if you ensure that the XML namespaces for the .xsd files included in your project match the XML namespaces identified for the XML Schema set in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64acf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="64acf-119">See also</span></span>

- [<span data-ttu-id="64acf-120">“错误列表”窗口</span><span class="sxs-lookup"><span data-stu-id="64acf-120">Error List Window</span></span>](/visualstudio/ide/reference/error-list-window)
- [<span data-ttu-id="64acf-121">XML</span><span class="sxs-lookup"><span data-stu-id="64acf-121">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
