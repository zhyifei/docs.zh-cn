---
title: 如何：在字符串 Visual Basic 中搜索
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: fe9e50dc5458fdf8546094e5f41c2f001f1d2791
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700063"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="29221-102">如何：在字符串中搜索（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="29221-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="29221-103">本文举例说明如何在 Visual Basic 中的字符串内进行搜索。</span><span class="sxs-lookup"><span data-stu-id="29221-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="29221-104">示例</span><span class="sxs-lookup"><span data-stu-id="29221-104">Example</span></span>

<span data-ttu-id="29221-105">此示例对 <xref:System.String> 对象调用 <xref:System.String.IndexOf%2A> 方法，以报告子字符串的第一个匹配项的索引：</span><span class="sxs-lookup"><span data-stu-id="29221-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="29221-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="29221-106">Robust programming</span></span>

<span data-ttu-id="29221-107"><xref:System.String.IndexOf%2A> 方法返回子字符串的第一个匹配项的第一个字符的位置。</span><span class="sxs-lookup"><span data-stu-id="29221-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="29221-108">索引从0开始，这意味着字符串的第一个字符的索引为0。</span><span class="sxs-lookup"><span data-stu-id="29221-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="29221-109">如果 <xref:System.String.IndexOf%2A> 未找到子字符串，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="29221-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="29221-110"><xref:System.String.IndexOf%2A> 方法区分大小写，并使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="29221-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="29221-111">为了获得最佳的错误控制，你可能需要将字符串搜索包含 `Try` 在[Try .。。Catch .。。Finally 语句](../../../language-reference/statements/try-catch-finally-statement.md)构造。</span><span class="sxs-lookup"><span data-stu-id="29221-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="29221-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29221-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="29221-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="29221-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="29221-114">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="29221-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="29221-115">字符串</span><span class="sxs-lookup"><span data-stu-id="29221-115">Strings</span></span>](index.md)
