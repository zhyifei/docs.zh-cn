---
title: 投影运算 (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: a044982c21246fd4e8c1cbdbb9801ae7b29d05c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335385"
---
# <a name="projection-operations-c"></a><span data-ttu-id="6ac40-102">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="6ac40-102">Projection Operations (C#)</span></span>
<span data-ttu-id="6ac40-103">投影是指将对象转换为一种新形式的操作，该形式通常只包含那些将随后使用的属性。</span><span class="sxs-lookup"><span data-stu-id="6ac40-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="6ac40-104">通过使用投影，您可以构造从每个对象生成的新类型。</span><span class="sxs-lookup"><span data-stu-id="6ac40-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="6ac40-105">可以投影属性，并对该属性执行数学函数。</span><span class="sxs-lookup"><span data-stu-id="6ac40-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="6ac40-106">还可以在不更改原始对象的情况下投影该对象。</span><span class="sxs-lookup"><span data-stu-id="6ac40-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="6ac40-107">下面一节列出了执行投影的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="6ac40-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ac40-108">方法</span><span class="sxs-lookup"><span data-stu-id="6ac40-108">Methods</span></span>  
  
|<span data-ttu-id="6ac40-109">方法名</span><span class="sxs-lookup"><span data-stu-id="6ac40-109">Method Name</span></span>|<span data-ttu-id="6ac40-110">描述</span><span class="sxs-lookup"><span data-stu-id="6ac40-110">Description</span></span>|<span data-ttu-id="6ac40-111">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="6ac40-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="6ac40-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="6ac40-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="6ac40-113">选择</span><span class="sxs-lookup"><span data-stu-id="6ac40-113">Select</span></span>|<span data-ttu-id="6ac40-114">投影基于转换函数的值。</span><span class="sxs-lookup"><span data-stu-id="6ac40-114">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6ac40-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="6ac40-115">SelectMany</span></span>|<span data-ttu-id="6ac40-116">投影基于转换函数的值序列，然后将它们展平为一个序列。</span><span class="sxs-lookup"><span data-stu-id="6ac40-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="6ac40-117">使用多个 `from` 子句</span><span class="sxs-lookup"><span data-stu-id="6ac40-117">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="6ac40-118">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="6ac40-118">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="6ac40-119">选择</span><span class="sxs-lookup"><span data-stu-id="6ac40-119">Select</span></span>  
 <span data-ttu-id="6ac40-120">下面的示例使用 `select` 子句来投影字符串列表中每个字符串的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="6ac40-120">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="6ac40-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="6ac40-121">SelectMany</span></span>  
 <span data-ttu-id="6ac40-122">下面的示例使用多个 `from` 子句来投影字符串列表中每个字符串中的每个单词。</span><span class="sxs-lookup"><span data-stu-id="6ac40-122">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="6ac40-123">Select 与 SelectMany</span><span class="sxs-lookup"><span data-stu-id="6ac40-123">Select versus SelectMany</span></span>  
 <span data-ttu-id="6ac40-124">`Select()` 和 `SelectMany()` 的工作都是依据源值生成一个或多个结果值。</span><span class="sxs-lookup"><span data-stu-id="6ac40-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="6ac40-125">`Select()` 为每个源值生成一个结果值。</span><span class="sxs-lookup"><span data-stu-id="6ac40-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="6ac40-126">因此，总体结果是一个与源集合具有相同元素数目的集合。</span><span class="sxs-lookup"><span data-stu-id="6ac40-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="6ac40-127">与之相反，`SelectMany()` 生成单个总体结果，其中包含来自每个源值的串联子集合。</span><span class="sxs-lookup"><span data-stu-id="6ac40-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="6ac40-128">作为参数传递到 `SelectMany()` 的转换函数必须为每个源值返回一个可枚举值序列。</span><span class="sxs-lookup"><span data-stu-id="6ac40-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="6ac40-129">然后，`SelectMany()` 串联这些可枚举序列，以创建一个大的序列。</span><span class="sxs-lookup"><span data-stu-id="6ac40-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="6ac40-130">下面两个插图演示了这两个方法的操作之间的概念性区别。</span><span class="sxs-lookup"><span data-stu-id="6ac40-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="6ac40-131">在每种情况下，假定选择器（转换）函数从每个源值中选择一个由花卉数据组成的数组。</span><span class="sxs-lookup"><span data-stu-id="6ac40-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="6ac40-132">下图描述 `Select()` 如何返回一个与源集合具有相同元素数目的集合。</span><span class="sxs-lookup"><span data-stu-id="6ac40-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 <span data-ttu-id="6ac40-133">![Select() 的操作的概念图](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span><span class="sxs-lookup"><span data-stu-id="6ac40-133">![Conceptual illustration of the action of Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span></span>  
  
 <span data-ttu-id="6ac40-134">下图描述 `SelectMany()` 如何将中间数组序列串联为一个最终结果值，其中包含每个中间数组中的每个值。</span><span class="sxs-lookup"><span data-stu-id="6ac40-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 <span data-ttu-id="6ac40-135">![显示 SelectMany() 的操作的图。](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span><span class="sxs-lookup"><span data-stu-id="6ac40-135">![Graphic showing the action of SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span></span>  
  
### <a name="code-example"></a><span data-ttu-id="6ac40-136">代码示例</span><span class="sxs-lookup"><span data-stu-id="6ac40-136">Code Example</span></span>  
 <span data-ttu-id="6ac40-137">下面的示例比较 `Select()` 和 `SelectMany()` 的行为。</span><span class="sxs-lookup"><span data-stu-id="6ac40-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="6ac40-138">代码通过从源集合的每个花卉名称列表中提取前两项来创建一个“花束”。</span><span class="sxs-lookup"><span data-stu-id="6ac40-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="6ac40-139">此示例中，transform 函数 <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> 使用的“单值”本身即是值的集合。</span><span class="sxs-lookup"><span data-stu-id="6ac40-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="6ac40-140">这需要额外的 `foreach` 循环，以便枚举每个子序列中的每个字符串。</span><span class="sxs-lookup"><span data-stu-id="6ac40-140">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********              
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ac40-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac40-141">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="6ac40-142">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="6ac40-142">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="6ac40-143">select 子句</span><span class="sxs-lookup"><span data-stu-id="6ac40-143">select clause</span></span>](../../../../csharp/language-reference/keywords/select-clause.md)  
 [<span data-ttu-id="6ac40-144">如何：从多个源填充对象集合 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6ac40-144">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 [<span data-ttu-id="6ac40-145">如何：使用组将一个文件拆分成多个文件 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6ac40-145">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
