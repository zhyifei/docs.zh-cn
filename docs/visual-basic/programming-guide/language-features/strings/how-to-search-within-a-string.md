---
title: 如何：字符串 (Visual Basic 中) 内的搜索
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: c150299efe07809d0d33edf882771f552c3e5b63
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982006"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="47dd0-102">如何：字符串 (Visual Basic 中) 内的搜索</span><span class="sxs-lookup"><span data-stu-id="47dd0-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="47dd0-103">此示例调用<xref:System.String.IndexOf%2A>方法<xref:System.String>要报告的子字符串的第一个匹配项的索引对象。</span><span class="sxs-lookup"><span data-stu-id="47dd0-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47dd0-104">示例</span><span class="sxs-lookup"><span data-stu-id="47dd0-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="47dd0-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="47dd0-105">Compiling the Code</span></span>  
 <span data-ttu-id="47dd0-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="47dd0-106">This example requires:</span></span>  
  
-   <span data-ttu-id="47dd0-107">`Imports`语句指定<xref:System>命名空间。</span><span class="sxs-lookup"><span data-stu-id="47dd0-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="47dd0-108">有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="47dd0-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="47dd0-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="47dd0-109">Robust Programming</span></span>  
 <span data-ttu-id="47dd0-110"><xref:System.String.IndexOf%2A>方法报告的子字符串的第一个匹配项的第一个字符位置。</span><span class="sxs-lookup"><span data-stu-id="47dd0-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="47dd0-111">索引是基于 0 的这意味着字符串的第一个字符的索引为 0。</span><span class="sxs-lookup"><span data-stu-id="47dd0-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="47dd0-112">如果<xref:System.String.IndexOf%2A>未找到子字符串，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="47dd0-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="47dd0-113"><xref:System.String.IndexOf%2A>方法区分大小写，并使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="47dd0-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="47dd0-114">为了优化错误控制，你可能想要在使用字符串搜索`Try`块[尝试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)构造。</span><span class="sxs-lookup"><span data-stu-id="47dd0-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47dd0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="47dd0-115">See also</span></span>
- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="47dd0-116">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="47dd0-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="47dd0-117">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="47dd0-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="47dd0-118">字符串</span><span class="sxs-lookup"><span data-stu-id="47dd0-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
