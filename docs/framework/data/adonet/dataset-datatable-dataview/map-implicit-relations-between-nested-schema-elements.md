---
title: 映射嵌套架构元素之间的隐式关系
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 3c0b5356479d31a3caad8438618e7cf7dc4e10e8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485568"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="3c565-102">映射嵌套架构元素之间的隐式关系</span><span class="sxs-lookup"><span data-stu-id="3c565-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="3c565-103">XML 架构定义语言 (XSD) 架构可以具有相互嵌套的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="3c565-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="3c565-104">在这种情况下，映射过程将应用默认映射并在 <xref:System.Data.DataSet> 中创建以下内容：</span><span class="sxs-lookup"><span data-stu-id="3c565-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="3c565-105">为每个复杂类型（父和子）创建一个表。</span><span class="sxs-lookup"><span data-stu-id="3c565-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="3c565-106">一个附加主键列每个表定义的父级上不存在任何唯一约束，如果名为*TableName*id （_i) 其中*TableName*是父表的名称。</span><span class="sxs-lookup"><span data-stu-id="3c565-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="3c565-107">为主键将附加列标识父表上的主键约束 (通过设置**IsPrimaryKey**属性设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="3c565-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="3c565-108">命名约束的约束*#* 其中*#* 是 1、 2、 3，依此类推。</span><span class="sxs-lookup"><span data-stu-id="3c565-108">The constraint is named Constraint*#* where *#* is 1, 2, 3, and so on.</span></span> <span data-ttu-id="3c565-109">例如，第一个约束的默认名称为 Constraint1。</span><span class="sxs-lookup"><span data-stu-id="3c565-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="3c565-110">在子表上创建外键约束，该约束将附加列标识为引用父表主键的外键。</span><span class="sxs-lookup"><span data-stu-id="3c565-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="3c565-111">命名约束*ParentTable_ChildTable*其中*ParentTable*是父表的名称并*ChildTable*是子表的名称。</span><span class="sxs-lookup"><span data-stu-id="3c565-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="3c565-112">在父表和子表之间创建数据关系。</span><span class="sxs-lookup"><span data-stu-id="3c565-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="3c565-113">下面的示例演示一个架构位置**OrderDetail**是子元素的**顺序**。</span><span class="sxs-lookup"><span data-stu-id="3c565-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
   <xs:complexType>  
     <xs:choice maxOccurs="unbounded">  
       <xs:element name="Order">  
         <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="3c565-114">XML 架构映射过程中创建以下**数据集**:</span><span class="sxs-lookup"><span data-stu-id="3c565-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="3c565-115">**顺序**和一个**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="3c565-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="3c565-116">Unique 约束**顺序**表。</span><span class="sxs-lookup"><span data-stu-id="3c565-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="3c565-117">请注意， **IsPrimaryKey**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="3c565-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="3c565-118">上的外键约束**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="3c565-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="3c565-119">之间的关系**顺序**并**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="3c565-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="3c565-120">**嵌套**为此关系的属性设置为**True**因为**顺序**并**OrderDetail**元素都嵌套在架构.</span><span class="sxs-lookup"><span data-stu-id="3c565-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3c565-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c565-121">See Also</span></span>  
 [<span data-ttu-id="3c565-122">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="3c565-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="3c565-123">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="3c565-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="3c565-124">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="3c565-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
