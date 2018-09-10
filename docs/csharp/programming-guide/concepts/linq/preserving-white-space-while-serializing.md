---
title: 在序列化3时保留空格
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 7fd0a38d2a9ed8c4712b8e9a03a24a23b408f38a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267084"
---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="bbfac-102">在序列化时保留空白</span><span class="sxs-lookup"><span data-stu-id="bbfac-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="bbfac-103">本主题描述在序列化 XML 树时如何控制空白。</span><span class="sxs-lookup"><span data-stu-id="bbfac-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="bbfac-104">一种常见方案是，读取缩进式 XML，创建不含任何空白符文本节点（即不保留空白符）的内存中 XML 树，对 XML 执行一些操作，再保存带缩进的 XML。</span><span class="sxs-lookup"><span data-stu-id="bbfac-104">A common scenario is to read indented XML, create an in-memory XML tree without any white-space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="bbfac-105">在序列化带格式的 XML 时，只保留 XML 树中有意义的空白。</span><span class="sxs-lookup"><span data-stu-id="bbfac-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="bbfac-106">这是 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="bbfac-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="bbfac-107">另一个常见的情况是读取和修改已经有意缩进的 XML。</span><span class="sxs-lookup"><span data-stu-id="bbfac-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="bbfac-108">您可能不想以任何方式更改这种缩进。</span><span class="sxs-lookup"><span data-stu-id="bbfac-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="bbfac-109">若要在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中执行此操作，您要在加载或解析 XML 时保留空白，并在序列化 XML 时禁用格式设置。</span><span class="sxs-lookup"><span data-stu-id="bbfac-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="bbfac-110">用于序列化 XML 树的方法的空白符行为</span><span class="sxs-lookup"><span data-stu-id="bbfac-110">White-Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="bbfac-111"><xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq.XDocument> 类中的以下方法用于序列化 XML 树。</span><span class="sxs-lookup"><span data-stu-id="bbfac-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="bbfac-112">可以将 XML 树序列化为文件、<xref:System.IO.TextReader> 或 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="bbfac-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="bbfac-113">`ToString` 方法序列化为字符串。</span><span class="sxs-lookup"><span data-stu-id="bbfac-113">The `ToString` method serializes to a string.</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="bbfac-114">如果方法不接受 <xref:System.Xml.Linq.SaveOptions> 作为参数，那么该方法将格式化（缩进）序列化的 XML。</span><span class="sxs-lookup"><span data-stu-id="bbfac-114">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="bbfac-115">在这种情况下，将丢弃 XML 树中所有无意义的空白。</span><span class="sxs-lookup"><span data-stu-id="bbfac-115">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="bbfac-116">如果方法接受 <xref:System.Xml.Linq.SaveOptions> 作为参数，那么您可以指定不格式化（缩进）序列化的 XML。</span><span class="sxs-lookup"><span data-stu-id="bbfac-116">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="bbfac-117">在这种情况下，将保留 XML 树中的所有空白。</span><span class="sxs-lookup"><span data-stu-id="bbfac-117">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfac-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbfac-118">See Also</span></span>

- [<span data-ttu-id="bbfac-119">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="bbfac-119">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
