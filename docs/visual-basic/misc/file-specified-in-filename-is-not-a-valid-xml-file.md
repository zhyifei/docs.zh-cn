---
title: 在 FileName 中指定的文件不是有效的 XML 文件
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 89499b07e767bd0b3a777db4e5155f64a4357f0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58921268"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="d5843-102">在 FileName 中指定的文件不是有效的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="d5843-102">File specified in FileName is not a valid XML file</span></span>

<span data-ttu-id="d5843-103">所提供的文件名称不是有效的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d5843-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="d5843-104">若要指定允许的 XML 文档的结构和内容，可使用文档类型定义 (DTD)、Microsoft XML 数据缩减 (XDR) 架构或 XML 架构定义语言 (XSD) 架构。</span><span class="sxs-lookup"><span data-stu-id="d5843-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="d5843-105">XSD 架构是用于指定 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]中的 XML 语法的首选方式。</span><span class="sxs-lookup"><span data-stu-id="d5843-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>

> [!NOTE]
> <span data-ttu-id="d5843-106">在某些较早版本的 Visual Studio 中，“XML 设计器”  是针对类型化数据集和 XML 架构的设计器。</span><span class="sxs-lookup"><span data-stu-id="d5843-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="d5843-107">“XML 设计器”  仍可用于创建和编辑 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="d5843-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="d5843-108">但是，在 Visual Studio 2012 中，用于创建和编辑类型化数据集设计器是**数据集设计器**。</span><span class="sxs-lookup"><span data-stu-id="d5843-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="d5843-109">有关详细信息，请参阅[创建和编辑类型化数据集](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="d5843-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d5843-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d5843-110">To correct this error</span></span>

- <span data-ttu-id="d5843-111">检查你所提供的文件名是否正确。</span><span class="sxs-lookup"><span data-stu-id="d5843-111">Check that you are supplying the correct file name.</span></span>

- <span data-ttu-id="d5843-112">通过将你想要检查的 XML 文件加载到“XML 设计器” 中，检查指定文件是否包含有效的 XML。</span><span class="sxs-lookup"><span data-stu-id="d5843-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="d5843-113">从“XML”  菜单上，单击“验证 XML” 。</span><span class="sxs-lookup"><span data-stu-id="d5843-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="d5843-114">错误都显示在“输出列表” 中。</span><span class="sxs-lookup"><span data-stu-id="d5843-114">Errors are displayed in the **Task List**.</span></span>

- <span data-ttu-id="d5843-115">如果 XML 文件具有关联的 XML 架构，请检查显示在已定义结构中的元素，以及单个元素的内容是否符合架构中指定的已声明的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d5843-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5843-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5843-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="d5843-117">如何：分析文件路径</span><span class="sxs-lookup"><span data-stu-id="d5843-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)