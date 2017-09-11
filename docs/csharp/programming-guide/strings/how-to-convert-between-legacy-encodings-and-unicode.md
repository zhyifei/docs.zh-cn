---
title: "如何：在旧式编码与 Unicode 之间转换（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="2f79d-102">如何：在旧式编码与 Unicode 之间转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2f79d-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="2f79d-103">在 C# 中，内存中的所有字符串都被编码为 Unicode (UTF-16)。</span><span class="sxs-lookup"><span data-stu-id="2f79d-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="2f79d-104">将数据从存储加入到 `string` 对象时，数据将被自动转换为 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="2f79d-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="2f79d-105">如果数据仅包含从 0 到 127 的 ASCII 值，则无需其他操作即可转换。</span><span class="sxs-lookup"><span data-stu-id="2f79d-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="2f79d-106">但是，如果源文本包含扩展的 ASCII 字节值（从 128 到 255），则将默认根据当前代码页解释扩展字符。</span><span class="sxs-lookup"><span data-stu-id="2f79d-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="2f79d-107">若要指定应根据其他代码页解释源文本，请使用 <xref:System.Text.Encoding?displayProperty=fullName> 类，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2f79d-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f79d-108">示例</span><span class="sxs-lookup"><span data-stu-id="2f79d-108">Example</span></span>  
 <span data-ttu-id="2f79d-109">以下示例演示如何转换在 8 位 ASCII 中编码的文本文件，根据 Windows 代码页 737 解释源文本。</span><span class="sxs-lookup"><span data-stu-id="2f79d-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="2f79d-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f79d-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f79d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f79d-111">See Also</span></span>  
 [<span data-ttu-id="2f79d-112">字符串</span><span class="sxs-lookup"><span data-stu-id="2f79d-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

