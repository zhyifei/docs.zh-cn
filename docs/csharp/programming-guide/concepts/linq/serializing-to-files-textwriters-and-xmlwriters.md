---
title: 序列化为文件、TextWriter 和 XmlWriter1
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: c74dc7f429e4ae27f08f7acb6b3a6c39161aac71
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483546"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="077aa-102">序列化为文件、TextWriter 和 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="077aa-102">Serializing to Files, TextWriters, and XmlWriters</span></span>

<span data-ttu-id="077aa-103">可以将 XML 树序列化为 <xref:System.IO.File>、<xref:System.IO.TextWriter> 或 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="077aa-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>

<span data-ttu-id="077aa-104">可以使用 <xref:System.Xml.Linq.XDocument> 方法，将任何 XML 组件（包括 <xref:System.Xml.Linq.XElement> 和 `ToString`）序列化为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="077aa-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>

<span data-ttu-id="077aa-105">在序列化为字符串时，如果要禁止格式化，可以使用 <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="077aa-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="077aa-106">序列化为文件时，默认行为是格式化（缩进）生成的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="077aa-106">The default behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="077aa-107">缩进时，不会保留 XML 树中无意义的空白。</span><span class="sxs-lookup"><span data-stu-id="077aa-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="077aa-108">若要使用格式化方式进行序列化，请使用不将 <xref:System.Xml.Linq.SaveOptions> 作为参数的以下方法的重载之一：</span><span class="sxs-lookup"><span data-stu-id="077aa-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="077aa-109">如果要选择不在 XML 树中缩进，并保留无意义空白，请使用将 <xref:System.Xml.Linq.SaveOptions> 作为参数的以下方法的重载之一：</span><span class="sxs-lookup"><span data-stu-id="077aa-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

<span data-ttu-id="077aa-110">有关示例，请参见相应的参考主题。</span><span class="sxs-lookup"><span data-stu-id="077aa-110">For examples, see the appropriate reference topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="077aa-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="077aa-111">See also</span></span>

- [<span data-ttu-id="077aa-112">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="077aa-112">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
