---
title: 如何：指定要对哪些成员进行并发冲突测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: 9a1b4ab2dc28c569473eddbf50b96d10298d8d3c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310429"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="71afa-102">如何：指定要对哪些成员进行并发冲突测试</span><span class="sxs-lookup"><span data-stu-id="71afa-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="71afa-103">应用到三个枚举之一[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>属性上的<xref:System.Data.Linq.Mapping.ColumnAttribute>属性来指定哪些成员是否将要包括在更新检查的开放式并发冲突的检测。</span><span class="sxs-lookup"><span data-stu-id="71afa-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="71afa-104"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性（在设计时映射）与 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中的运行时并发功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="71afa-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="71afa-105">有关详细信息，请参阅[开放式并发：概述](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="71afa-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71afa-106">只要未将任何成员指定为 `IsVersion=true`，就会将原始成员值与当前数据库状态进行比较。</span><span class="sxs-lookup"><span data-stu-id="71afa-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="71afa-107">有关详细信息，请参阅 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="71afa-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="71afa-108">有关代码示例，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="71afa-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="71afa-109">始终使用此成员检测冲突</span><span class="sxs-lookup"><span data-stu-id="71afa-109">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="71afa-110">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="71afa-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="71afa-111">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性值设置为 `Always`。</span><span class="sxs-lookup"><span data-stu-id="71afa-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="71afa-112">永不使用此成员检测冲突</span><span class="sxs-lookup"><span data-stu-id="71afa-112">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="71afa-113">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="71afa-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="71afa-114">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性值设置为 `Never`。</span><span class="sxs-lookup"><span data-stu-id="71afa-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="71afa-115">仅在应用程序已更改此成员的值时才使用此成员检测冲突</span><span class="sxs-lookup"><span data-stu-id="71afa-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="71afa-116">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性 (Property) 添加到 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="71afa-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="71afa-117">将 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 属性值设置为 `WhenChanged`。</span><span class="sxs-lookup"><span data-stu-id="71afa-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71afa-118">示例</span><span class="sxs-lookup"><span data-stu-id="71afa-118">Example</span></span>  
 <span data-ttu-id="71afa-119">下面的示例指定在更新检查期间永远都不应该测试 `HomePage` 对象。</span><span class="sxs-lookup"><span data-stu-id="71afa-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="71afa-120">有关详细信息，请参阅 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="71afa-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="71afa-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="71afa-121">See also</span></span>

- [<span data-ttu-id="71afa-122">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="71afa-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="71afa-123">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="71afa-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
