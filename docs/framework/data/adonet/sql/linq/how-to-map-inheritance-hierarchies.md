---
title: 如何：映射继承层次结构
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 6f437b7f7ae6a414971edb497bc2c84c03674fe8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904041"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="fa0d8-102">如何：映射继承层次结构</span><span class="sxs-lookup"><span data-stu-id="fa0d8-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="fa0d8-103">若要在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中执行继承映射，您必须按以下步骤中的说明在继承层次结构的根类中指定属性 (Attribute) 和属性 (Attribute) 的属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-103">To implement inheritance mapping in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="fa0d8-104">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来映射继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-104">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span> <span data-ttu-id="fa0d8-105">请参阅[如何：使用 O/R 设计器配置继承](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa0d8-106">子类中不需要具有特殊属性 (Attribute) 或属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="fa0d8-107">请特别注意，子类不具有 <xref:System.Data.Linq.Mapping.TableAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="fa0d8-108">映射继承层次结构</span><span class="sxs-lookup"><span data-stu-id="fa0d8-108">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="fa0d8-109">向根类添加 <xref:System.Data.Linq.Mapping.TableAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="fa0d8-110">为层次结构中的每个类添加 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性，同样是添加到根类中。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="fa0d8-111">为每个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性 (Attribute)，定义一个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="fa0d8-112">此属性 (Property) 保存一个值，该值显示在数据库表的 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 列中，用来指示该行数据所属的类或子类。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="fa0d8-113">为每个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性 (Attribute)，也添加一个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="fa0d8-114">此属性 (Property) 保存一个值，此值指定键值所表示的类或子类。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="fa0d8-115">仅在其中一个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 属性 (Attribute) 上，添加一个 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="fa0d8-116">此属性用于指定*回退*的映射，在数据库表中的鉴别器值不匹配任何<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>在继承映射中的值。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="fa0d8-117">为 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 属性 (Attribute) 添加一个 <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="fa0d8-118">此属性 (Property) 表示这是保存 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 值的列。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa0d8-119">示例</span><span class="sxs-lookup"><span data-stu-id="fa0d8-119">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa0d8-120">如果使用的 Visual Studio，则可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]配置继承。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-120">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to configure inheritance.</span></span> <span data-ttu-id="fa0d8-121">请参阅[如何：使用 O/R 设计器配置继承](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="fa0d8-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="fa0d8-122">在下面的代码示例中，`Vehicle` 定义为根类，并且已执行前面的步骤来说明 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 的层次结构。</span><span class="sxs-lookup"><span data-stu-id="fa0d8-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fa0d8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0d8-123">See also</span></span>

- [<span data-ttu-id="fa0d8-124">层次结构支持</span><span class="sxs-lookup"><span data-stu-id="fa0d8-124">Inheritance Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)
- [<span data-ttu-id="fa0d8-125">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="fa0d8-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
