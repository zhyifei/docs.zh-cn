---
title: '&lt;权限&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: bcec5d968f5d0c5400c28e772df151b164888a47
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205164"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="7faf3-102">&lt;权限&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7faf3-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="7faf3-103">指定成员所需的权限。</span><span class="sxs-lookup"><span data-stu-id="7faf3-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7faf3-104">语法</span><span class="sxs-lookup"><span data-stu-id="7faf3-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7faf3-105">参数</span><span class="sxs-lookup"><span data-stu-id="7faf3-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="7faf3-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="7faf3-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="7faf3-107">编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="7faf3-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="7faf3-108">将`member`用引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="7faf3-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="7faf3-109">对成员访问权限的说明。</span><span class="sxs-lookup"><span data-stu-id="7faf3-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7faf3-110">备注</span><span class="sxs-lookup"><span data-stu-id="7faf3-110">Remarks</span></span>  
 <span data-ttu-id="7faf3-111">使用`<permission>`标记来记录成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7faf3-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="7faf3-112">使用<xref:System.Security.PermissionSet>类，以指定对成员的访问。</span><span class="sxs-lookup"><span data-stu-id="7faf3-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="7faf3-113">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="7faf3-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7faf3-114">示例</span><span class="sxs-lookup"><span data-stu-id="7faf3-114">Example</span></span>  
 <span data-ttu-id="7faf3-115">此示例使用`<permission>`标记来描述该<xref:System.Security.Permissions.FileIOPermission>所需的`ReadFile`方法。</span><span class="sxs-lookup"><span data-stu-id="7faf3-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7faf3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7faf3-116">See Also</span></span>  
 [<span data-ttu-id="7faf3-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="7faf3-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
