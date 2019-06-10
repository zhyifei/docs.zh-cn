---
title: C#1 中默认命名空间的范围
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 2eee1b0c79f585710962d8e84fe584bca6b8228b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483615"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="75e0e-102">C\# 中默认命名空间的范围</span><span class="sxs-lookup"><span data-stu-id="75e0e-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="75e0e-103">XML 树中表示的默认命名空间不在查询范围内。</span><span class="sxs-lookup"><span data-stu-id="75e0e-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="75e0e-104">如果您的 XML 在默认命名空间内，仍须声明一个 <xref:System.Xml.Linq.XNamespace> 变量，并将该变量与本地名称组合在一起，生成一个限定名，在查询中使用。</span><span class="sxs-lookup"><span data-stu-id="75e0e-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="75e0e-105">查询 XML 树时遇到的一个最常见问题是，如果 XML 树具有默认命名空间，开发人员在编写查询时，有时会将 XML 视为不在命名空间内。</span><span class="sxs-lookup"><span data-stu-id="75e0e-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="75e0e-106">本主题的第一个示例集演示一种加载但是按不正确方式查询默认命名空间中的 XML 的典型方式。</span><span class="sxs-lookup"><span data-stu-id="75e0e-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="75e0e-107">第二个示例集演示必需的更正，以便可以查询命名空间中的 XML。</span><span class="sxs-lookup"><span data-stu-id="75e0e-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75e0e-108">示例</span><span class="sxs-lookup"><span data-stu-id="75e0e-108">Example</span></span>  
 <span data-ttu-id="75e0e-109">此示例演示如何在命名空间中创建 XML 和一个返回空结果集的查询。</span><span class="sxs-lookup"><span data-stu-id="75e0e-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="75e0e-110">代码</span><span class="sxs-lookup"><span data-stu-id="75e0e-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="75e0e-111">注释</span><span class="sxs-lookup"><span data-stu-id="75e0e-111">Comments</span></span>  
 <span data-ttu-id="75e0e-112">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="75e0e-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="75e0e-113">示例</span><span class="sxs-lookup"><span data-stu-id="75e0e-113">Example</span></span>  
 <span data-ttu-id="75e0e-114">本示例演示如何在命名空间中创建 XML 和一个正确编码的查询。</span><span class="sxs-lookup"><span data-stu-id="75e0e-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="75e0e-115">与上述不正确编码的示例相比，使用 C# 时的正确方法是声明和初始化一个 <xref:System.Xml.Linq.XNamespace> 对象，并在指定 <xref:System.Xml.Linq.XName> 对象时使用它。</span><span class="sxs-lookup"><span data-stu-id="75e0e-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="75e0e-116">在这种情况下，<xref:System.Xml.Linq.XContainer.Elements%2A> 方法的参数是一个 <xref:System.Xml.Linq.XName> 对象。</span><span class="sxs-lookup"><span data-stu-id="75e0e-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="75e0e-117">代码</span><span class="sxs-lookup"><span data-stu-id="75e0e-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="75e0e-118">注释</span><span class="sxs-lookup"><span data-stu-id="75e0e-118">Comments</span></span>  
 <span data-ttu-id="75e0e-119">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="75e0e-119">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="75e0e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="75e0e-120">See also</span></span>

- [<span data-ttu-id="75e0e-121">使用 XML 命名空间 (C#)</span><span class="sxs-lookup"><span data-stu-id="75e0e-121">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)
