---
title: 如何：验证文件的名称和在 Visual Basic 中的路径
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: d29553071d68319d754406b3104da6e096f908fd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975519"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="2178c-102">如何：验证文件的名称和在 Visual Basic 中的路径</span><span class="sxs-lookup"><span data-stu-id="2178c-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="2178c-103">此示例返回`Boolean`值，该值指示字符串是否表示文件名称或路径。</span><span class="sxs-lookup"><span data-stu-id="2178c-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="2178c-104">验证检查名称是否包含不允许使用的文件系统的字符。</span><span class="sxs-lookup"><span data-stu-id="2178c-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2178c-105">示例</span><span class="sxs-lookup"><span data-stu-id="2178c-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="2178c-106">此示例不会检查，如果名称不正确放置冒号或目录没有名称或名称的长度超过系统定义的最大长度。</span><span class="sxs-lookup"><span data-stu-id="2178c-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="2178c-107">它也不会检查应用程序是否具有指定名称的文件系统资源的访问权。</span><span class="sxs-lookup"><span data-stu-id="2178c-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2178c-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2178c-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="2178c-109">在 Visual Basic 中验证字符串</span><span class="sxs-lookup"><span data-stu-id="2178c-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
