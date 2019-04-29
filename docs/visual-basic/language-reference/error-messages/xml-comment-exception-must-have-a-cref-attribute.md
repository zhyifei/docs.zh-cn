---
title: XML 注释异常必须具有“cref”特性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766598"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="ef731-102">XML 注释异常必须具有“cref”特性</span><span class="sxs-lookup"><span data-stu-id="ef731-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="ef731-103">\<异常 > 标记提供了一种方法来记录方法可能引发的异常。</span><span class="sxs-lookup"><span data-stu-id="ef731-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="ef731-104">所需`cref`特性将指定的成员，它由文档生成器检查名称。</span><span class="sxs-lookup"><span data-stu-id="ef731-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="ef731-105">如果存在该成员，它被转换为文档文件中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="ef731-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="ef731-106">**错误 ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="ef731-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef731-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ef731-107">To correct this error</span></span>  
  
- <span data-ttu-id="ef731-108">添加`cref`属性为异常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef731-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ef731-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef731-109">See also</span></span>

- [<span data-ttu-id="ef731-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="ef731-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="ef731-111">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="ef731-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="ef731-112">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ef731-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
