---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 7125f6079811421bc5a7abdce2e13d591a299630
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269323"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="9f81e-102">\<备注 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f81e-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="9f81e-103">指定成员的备注部分。</span><span class="sxs-lookup"><span data-stu-id="9f81e-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f81e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f81e-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f81e-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f81e-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="9f81e-106">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="9f81e-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f81e-107">备注</span><span class="sxs-lookup"><span data-stu-id="9f81e-107">Remarks</span></span>  
 <span data-ttu-id="9f81e-108">使用`<remarks>`标记添加有关某个类型，对与指定的信息进行了补充[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)。</span><span class="sxs-lookup"><span data-stu-id="9f81e-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="9f81e-109">此信息显示在对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="9f81e-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="9f81e-110">对象浏览器有关的信息，请参阅[查看代码结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="9f81e-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="9f81e-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="9f81e-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f81e-112">示例</span><span class="sxs-lookup"><span data-stu-id="9f81e-112">Example</span></span>  
 <span data-ttu-id="9f81e-113">此示例使用`<remarks>`标记解释`UpdateRecord`方法执行。</span><span class="sxs-lookup"><span data-stu-id="9f81e-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9f81e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f81e-114">See also</span></span>
- [<span data-ttu-id="9f81e-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="9f81e-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
