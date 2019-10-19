---
title: 扩展索引器属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 660cebadc78d260350f2849f7f4926f9cef7c8d2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582187"
---
# <a name="extension-indexer-property-visual-basic"></a>扩展索引器属性 (Visual Basic)
提供对集合中各个元素的访问。  
  
## <a name="syntax"></a>语法  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`object`|必须的。 可查询的集合。 即实现 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Linq.IQueryable%601> 的集合。|  
|(|必须的。 表示索引器属性的开头。|  
|`index`|必须的。 一个整数表达式，指定集合的元素的从零开始的位置。|  
|)|必须的。 表示索引器属性的结尾。|  
  
## <a name="return-value"></a>返回值  
 集合中指定位置的对象; 如果索引超出范围，则 `Nothing`。  
  
## <a name="remarks"></a>备注  
 可以使用扩展索引器属性访问集合中的单个元素。 此索引器属性通常用于 XML 轴属性的输出。 XML 子和 XML 子代轴属性返回 <xref:System.Xml.Linq.XElement> 对象的集合或属性值。  
  
 Visual Basic 编译器将扩展索引器属性转换为对 `ElementAtOrDefault` 方法的调用。 与数组索引器不同，如果索引超出范围，则 `ElementAtOrDefault` 方法返回 `Nothing`。 如果无法轻松确定集合中的元素数，则此行为很有用。  
  
 此索引器属性类似于实现 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Linq.IQueryable%601> 的集合的扩展属性：只有当集合没有索引器或默认属性时，才使用此属性。  
  
 若要访问 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XAttribute> 对象集合中第一个元素的值，可以使用 XML `Value` 属性。 有关详细信息，请参阅[XML Value 属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用扩展索引器访问 <xref:System.Xml.Linq.XElement> 对象的集合中的第二个子节点。 使用子轴属性访问该集合，该属性将获取 `contact` 对象中名为 `phone` 的所有子元素。  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 此代码显示以下文本：  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.Linq.XElement>
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
