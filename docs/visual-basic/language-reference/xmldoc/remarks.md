---
title: <remarks> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524674"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="0c855-102">\<remarks > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="0c855-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="0c855-103">为成员指定备注部分。</span><span class="sxs-lookup"><span data-stu-id="0c855-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c855-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c855-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c855-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c855-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="0c855-106">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="0c855-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c855-107">备注</span><span class="sxs-lookup"><span data-stu-id="0c855-107">Remarks</span></span>  
 <span data-ttu-id="0c855-108">使用 `<remarks>` 标记添加有关类型的信息，从而补充[\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)指定的信息。</span><span class="sxs-lookup"><span data-stu-id="0c855-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="0c855-109">此信息显示在对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="0c855-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="0c855-110">有关对象浏览器的信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="0c855-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="0c855-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="0c855-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c855-112">示例</span><span class="sxs-lookup"><span data-stu-id="0c855-112">Example</span></span>  
 <span data-ttu-id="0c855-113">此示例使用 `<remarks>` 标记解释 `UpdateRecord` 方法的作用。</span><span class="sxs-lookup"><span data-stu-id="0c855-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0c855-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c855-114">See also</span></span>

- [<span data-ttu-id="0c855-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="0c855-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
