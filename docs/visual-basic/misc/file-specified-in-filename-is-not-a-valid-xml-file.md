---
title: "在 FileName 中指定的文件不是有效的 XML 文件 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b46b9d896f0dce401992e8a20e040b85091ba5d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="3cfe5-102">在 FileName 中指定的文件不是有效的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="3cfe5-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="3cfe5-103">所提供的文件名称不是有效的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="3cfe5-104">若要指定允许的 XML 文档的结构和内容，可使用文档类型定义 (DTD)、Microsoft XML 数据缩减 (XDR) 架构或 XML 架构定义语言 (XSD) 架构。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="3cfe5-105">XSD 架构是用于指定 XML 语法中的首选的方式[!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cfe5-106">在某些较早版本的 Visual Studio 中，“XML 设计器” **** 是针对类型化数据集和 XML 架构的设计器。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="3cfe5-107">“XML 设计器” **** 仍可用于创建和编辑 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="3cfe5-108">但是，在[!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)]，用于创建和编辑类型化数据集设计器是**数据集设计器**。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-108">However, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="3cfe5-109">有关详细信息，请参阅[创建和编辑类型化数据集](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets)。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3cfe5-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3cfe5-110">To correct this error</span></span>  
  
-   <span data-ttu-id="3cfe5-111">检查你所提供的文件名是否正确。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="3cfe5-112">通过将你想要检查的 XML 文件加载到“XML 设计器” ****中，检查指定文件是否包含有效的 XML。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="3cfe5-113">从“XML” **** 菜单上，单击“验证 XML” ****。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="3cfe5-114">错误都显示在“输出列表” ****中。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="3cfe5-115">如果 XML 文件具有关联的 XML 架构，请检查显示在已定义结构中的元素，以及单个元素的内容是否符合架构中指定的已声明的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3cfe5-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cfe5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cfe5-116">See Also</span></span>  
 <span data-ttu-id="3cfe5-117"><xref:System.Xml></xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="3cfe5-117"><xref:System.Xml></span></span>   
<span data-ttu-id="3cfe5-118"> [如何：分析文件路径](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span><span class="sxs-lookup"><span data-stu-id="3cfe5-118"> [How to: Parse File Paths](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span></span>
