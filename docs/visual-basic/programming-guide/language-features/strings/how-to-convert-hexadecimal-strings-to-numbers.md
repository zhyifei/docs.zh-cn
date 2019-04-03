---
title: 如何：将十六进制字符串转换为数字 (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: 350cfb59a01a4526a2b679fabfa2d49aeab23c19
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813084"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="813c6-102">如何：将十六进制字符串转换为数字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="813c6-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="813c6-103">此示例将十六进制字符串转换为整数使用<xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="813c6-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="813c6-104">将十六进制字符串转换为数字</span><span class="sxs-lookup"><span data-stu-id="813c6-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="813c6-105">使用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法将转换为整数的基数为 16 表达的数字。</span><span class="sxs-lookup"><span data-stu-id="813c6-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="813c6-106">第一个参数<xref:System.Convert.ToInt32(System.String,System.Int32)>方法是要转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="813c6-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="813c6-107">第二个参数用于描述; 表示的数字的基础十六进制是以 16 为基数。</span><span class="sxs-lookup"><span data-stu-id="813c6-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]  

- <span data-ttu-id="813c6-108">请注意，十六进制字符串有以下限制：</span><span class="sxs-lookup"><span data-stu-id="813c6-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="813c6-109">它不能包括`&h`前缀。</span><span class="sxs-lookup"><span data-stu-id="813c6-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="813c6-110">它不能包括`_`数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="813c6-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="813c6-111">如果前缀或数字分隔符的存在，调用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法会抛出<xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="813c6-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="813c6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="813c6-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
