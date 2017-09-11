---
title: "缓解：XML 架构验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 786e2d0d70aaead6d464d262ca43dade8db64a52
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="cdd61-102">缓解：XML 架构验证</span><span class="sxs-lookup"><span data-stu-id="cdd61-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="cdd61-103">在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中，如果使用复合键且有一个键为空，则 XSD 架构验证将检测是否违反唯一约束。</span><span class="sxs-lookup"><span data-stu-id="cdd61-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="cdd61-104">影响</span><span class="sxs-lookup"><span data-stu-id="cdd61-104">Impact</span></span>  
 <span data-ttu-id="cdd61-105">此更改的影响应该很小：根据架构规范，如果因使用具有空键的复合键违反了 `xsd:unique`，则会出现架构验证错误。</span><span class="sxs-lookup"><span data-stu-id="cdd61-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="cdd61-106">缓解操作</span><span class="sxs-lookup"><span data-stu-id="cdd61-106">Mitigation</span></span>  
 <span data-ttu-id="cdd61-107">是否在复合键具有一个空键的情况下检测架构验证错误是一项可配置的功能：</span><span class="sxs-lookup"><span data-stu-id="cdd61-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="cdd61-108">从面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用开始，默认情况下会启用架构验证错误的检测，但可以选择退出此行为，这样将不会检测架构验证错误。</span><span class="sxs-lookup"><span data-stu-id="cdd61-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="cdd61-109">在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 下运行但面向 [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 及更早版本的应用中，默认情况下不会检测架构验证错误，但可以选择加入此行为，这样将检测架构验证错误。</span><span class="sxs-lookup"><span data-stu-id="cdd61-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="cdd61-110">此行为可以通过使用 <xref:System.AppContext> 类定义 `System.Xml.IgnoreEmptyKeySequences` 开关的值来配置。</span><span class="sxs-lookup"><span data-stu-id="cdd61-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="cdd61-111">由于开关的默认值为 `false`（不忽略空键顺序），面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的应用可以通过使用下面的代码将开关的值设置为 `true` 以选择退出该行为。</span><span class="sxs-lookup"><span data-stu-id="cdd61-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 <span data-ttu-id="cdd61-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="cdd61-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span></span>  
  
 <span data-ttu-id="cdd61-113">对于面向 [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] 和更早版本的应用，由于开关的默认值为 `true`（忽略空键顺序），可以通过使用下面的代码将开关的值设置为 `false` 来确保具有空键的复合键生成架构验证错误。</span><span class="sxs-lookup"><span data-stu-id="cdd61-113">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 <span data-ttu-id="cdd61-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="cdd61-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd61-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd61-115">See Also</span></span>  
 [<span data-ttu-id="cdd61-116">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="cdd61-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

