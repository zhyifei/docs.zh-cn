---
title: UriTemplate 和 UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: 66463248f66457aa61ceea22afd003f7b93717e1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090508"
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="81d30-102">UriTemplate 和 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="81d30-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="81d30-103">Web 开发人员需要能够描述其服务所响应的 URI 的形状和布局。</span><span class="sxs-lookup"><span data-stu-id="81d30-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="81d30-104">Windows Communication Foundation (WCF) 添加两个新类，以帮助开发人员控制其 Uri。</span><span class="sxs-lookup"><span data-stu-id="81d30-104">Windows Communication Foundation (WCF) added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="81d30-105"><xref:System.UriTemplate> 和<xref:System.UriTemplateTable>构成 WCF 中基于 URI 的调度引擎的基础。</span><span class="sxs-lookup"><span data-stu-id="81d30-105"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in WCF.</span></span> <span data-ttu-id="81d30-106">这些类还可以在其自身，从而允许开发人员充分利用模板和 URI 映射机制而无需实现 WCF 服务使用。</span><span class="sxs-lookup"><span data-stu-id="81d30-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a WCF service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="81d30-107">模板</span><span class="sxs-lookup"><span data-stu-id="81d30-107">Templates</span></span>  
 <span data-ttu-id="81d30-108">模板是一种描述一组相对 URI 的方法。</span><span class="sxs-lookup"><span data-stu-id="81d30-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="81d30-109">下表中的一组 URI 模板演示如何定义一个检索各类天气信息的系统。</span><span class="sxs-lookup"><span data-stu-id="81d30-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="81d30-110">数据</span><span class="sxs-lookup"><span data-stu-id="81d30-110">Data</span></span>|<span data-ttu-id="81d30-111">模板</span><span class="sxs-lookup"><span data-stu-id="81d30-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="81d30-112">全国预报</span><span class="sxs-lookup"><span data-stu-id="81d30-112">National Forecast</span></span>|<span data-ttu-id="81d30-113">weather/national</span><span class="sxs-lookup"><span data-stu-id="81d30-113">weather/national</span></span>|  
|<span data-ttu-id="81d30-114">州预报</span><span class="sxs-lookup"><span data-stu-id="81d30-114">State Forecast</span></span>|<span data-ttu-id="81d30-115">weather/{state}</span><span class="sxs-lookup"><span data-stu-id="81d30-115">weather/{state}</span></span>|  
|<span data-ttu-id="81d30-116">城市预报</span><span class="sxs-lookup"><span data-stu-id="81d30-116">City Forecast</span></span>|<span data-ttu-id="81d30-117">weather/{state}/{city}</span><span class="sxs-lookup"><span data-stu-id="81d30-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="81d30-118">活动预报</span><span class="sxs-lookup"><span data-stu-id="81d30-118">Activity Forecast</span></span>|<span data-ttu-id="81d30-119">weather/{state}/{city}/{activity}</span><span class="sxs-lookup"><span data-stu-id="81d30-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="81d30-120">上表描述了一组结构相似的 URI。</span><span class="sxs-lookup"><span data-stu-id="81d30-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="81d30-121">每一项都是一个 URI 模板。</span><span class="sxs-lookup"><span data-stu-id="81d30-121">Each entry is a URI template.</span></span> <span data-ttu-id="81d30-122">大括号中的各段描述变量；</span><span class="sxs-lookup"><span data-stu-id="81d30-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="81d30-123">大括号之外的各段描述文本字符串。</span><span class="sxs-lookup"><span data-stu-id="81d30-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="81d30-124">WCF 模板类允许开发人员需要将传入的 URI，例如，"/ weather/wa/seattle/循环"，并将它匹配描述它的模板"/weather/{state}/{city}/{activity} / {city} / {活动}"。</span><span class="sxs-lookup"><span data-stu-id="81d30-124">The WCF template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="81d30-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="81d30-125">UriTemplate</span></span>  
 <span data-ttu-id="81d30-126"><xref:System.UriTemplate> 是包装 URI 模板的类。</span><span class="sxs-lookup"><span data-stu-id="81d30-126"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="81d30-127">其构造函数接受一个定义模板的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="81d30-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="81d30-128">此字符串包含具有下节所述格式的模板。</span><span class="sxs-lookup"><span data-stu-id="81d30-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="81d30-129"><xref:System.UriTemplate> 类提供一些方法，用于将传入的 URI 与模板进行匹配，根据模板生成 URI，检索在模板中使用的变量名集合，确定两个模板是否等效，返回模板的字符串。</span><span class="sxs-lookup"><span data-stu-id="81d30-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="81d30-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> 接受一个基址和一个候选 URI，并尝试将该 URI 与模板进行匹配。</span><span class="sxs-lookup"><span data-stu-id="81d30-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="81d30-131">如果匹配成功，则返回一个 <xref:System.UriTemplateMatch> 实例。</span><span class="sxs-lookup"><span data-stu-id="81d30-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="81d30-132"><xref:System.UriTemplateMatch> 对象包含一个基准 URI、候选 URI、查询参数的名称/值集合、相对路径段数组、匹配变量的名称/值集合、用于执行匹配操作的 <xref:System.UriTemplate> 实例、包含候选 URI 中任意不匹配部分的字符串（在模板有通配符时使用），以及一个与模板关联的对象。</span><span class="sxs-lookup"><span data-stu-id="81d30-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81d30-133">将候选 URI 与模板进行匹配时，<xref:System.UriTemplate> 类将忽略方案和端口号。</span><span class="sxs-lookup"><span data-stu-id="81d30-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="81d30-134">从模板生成 URI 的方法有两个，即 <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> 和 <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>。</span><span class="sxs-lookup"><span data-stu-id="81d30-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="81d30-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> 接受一个基址和一个参数的名称/值集合。</span><span class="sxs-lookup"><span data-stu-id="81d30-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="81d30-136">模板绑定后，这些参数将替换变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-136">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="81d30-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> 接受名称/值对，并从左向右替换他们。</span><span class="sxs-lookup"><span data-stu-id="81d30-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="81d30-138"><xref:System.UriTemplate.ToString> 返回模板字符串。</span><span class="sxs-lookup"><span data-stu-id="81d30-138"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="81d30-139"><xref:System.UriTemplate.PathSegmentVariableNames%2A> 属性包含变量名称的集合，这些变量就是模板字符串的路径段中所使用的变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="81d30-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> 接受一个 <xref:System.UriTemplate> 作为参数，并返回一个布尔值，该值指定两个模板是否等效。</span><span class="sxs-lookup"><span data-stu-id="81d30-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> <span data-ttu-id="81d30-141">有关详细信息，请参阅本主题后面的模板等效性部分。</span><span class="sxs-lookup"><span data-stu-id="81d30-141">For more information, see the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="81d30-142"><xref:System.UriTemplate> 旨在处理符合 HTTP URI 语法的任意 URI 方案。</span><span class="sxs-lookup"><span data-stu-id="81d30-142"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="81d30-143">下面这些示例都是支持的 URI 方案。</span><span class="sxs-lookup"><span data-stu-id="81d30-143">The following are examples of supported URI schemes.</span></span>  
  
- <span data-ttu-id="81d30-144">http://</span><span class="sxs-lookup"><span data-stu-id="81d30-144">http://</span></span>  
  
- <span data-ttu-id="81d30-145">https://</span><span class="sxs-lookup"><span data-stu-id="81d30-145">https://</span></span>  
  
- <span data-ttu-id="81d30-146">net.tcp://</span><span class="sxs-lookup"><span data-stu-id="81d30-146">net.tcp://</span></span>  
  
- <span data-ttu-id="81d30-147">net.pipe://</span><span class="sxs-lookup"><span data-stu-id="81d30-147">net.pipe://</span></span>  
  
- <span data-ttu-id="81d30-148">sb://</span><span class="sxs-lookup"><span data-stu-id="81d30-148">sb://</span></span>  
  
 <span data-ttu-id="81d30-149">诸如 file:// 和 urn:// 这样的方案不符合 HTTP URI 语法，它们与 URI 模板一起使用时，将导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="81d30-149">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="81d30-150">模板字符串语法</span><span class="sxs-lookup"><span data-stu-id="81d30-150">Template String Syntax</span></span>  
 <span data-ttu-id="81d30-151">模板分为三个部分：路径、可选查询和可选片段。</span><span class="sxs-lookup"><span data-stu-id="81d30-151">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="81d30-152">有关示例，请参见下面的模板：</span><span class="sxs-lookup"><span data-stu-id="81d30-152">For an example, see the following template:</span></span>  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 <span data-ttu-id="81d30-153">路径由“/weather/{state}/{city}”构成，查询由“?forecast={length}”构成，片段由“#frag1”构成。</span><span class="sxs-lookup"><span data-stu-id="81d30-153">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="81d30-154">在路径表达式中，首尾斜杠是可选的。</span><span class="sxs-lookup"><span data-stu-id="81d30-154">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="81d30-155">查询表达式和片段表达式可完全省略。</span><span class="sxs-lookup"><span data-stu-id="81d30-155">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="81d30-156">路径由一系列由分隔的段组成 '/'，每个段可包含文本值、 变量名 （写在 {大括号} 中） 或通配符 (编写为\*)。</span><span class="sxs-lookup"><span data-stu-id="81d30-156">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="81d30-157">在上一模板中，“\weather\”段为文本值，而“{state}”和“{city}”为变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-157">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="81d30-158">变量采用其大括号中的内容及其名称和更高版本可以使用来创建一个具体值替换它们*封闭的 URI*。</span><span class="sxs-lookup"><span data-stu-id="81d30-158">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="81d30-159">通配符是可选的但只能出现在 URI，它以逻辑方式匹配的其余部分路径"的末尾。</span><span class="sxs-lookup"><span data-stu-id="81d30-159">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="81d30-160">查询表达式（如果有）指定一系列用“&”分隔的无序名称/值对。</span><span class="sxs-lookup"><span data-stu-id="81d30-160">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="81d30-161">查询表达式的元素可以是文本对 (x=2) 或变量对 (x={var})。</span><span class="sxs-lookup"><span data-stu-id="81d30-161">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="81d30-162">只有查询的右侧可以有变量表达式。</span><span class="sxs-lookup"><span data-stu-id="81d30-162">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="81d30-163">不允许 {someName} = {someValue}。</span><span class="sxs-lookup"><span data-stu-id="81d30-163">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="81d30-164">不允许使用不成对的值 (?x)。</span><span class="sxs-lookup"><span data-stu-id="81d30-164">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="81d30-165">没有任何空的查询表达式和包含只包含一个查询表达式之间的区别？（两者都表示"任何查询"）。</span><span class="sxs-lookup"><span data-stu-id="81d30-165">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="81d30-166">片段表达式可以由文本值构成，不允许使用任何变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-166">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="81d30-167">模板字符串内的所有模板变量名都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81d30-167">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="81d30-168">模板变量名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="81d30-168">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="81d30-169">有效模板字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="81d30-169">Examples of valid template strings:</span></span>  
  
- <span data-ttu-id="81d30-170">""</span><span class="sxs-lookup"><span data-stu-id="81d30-170">""</span></span>  
  
- <span data-ttu-id="81d30-171">"/shoe"</span><span class="sxs-lookup"><span data-stu-id="81d30-171">"/shoe"</span></span>  
  
- <span data-ttu-id="81d30-172">"/shoe/\*"</span><span class="sxs-lookup"><span data-stu-id="81d30-172">"/shoe/\*"</span></span>  
  
- <span data-ttu-id="81d30-173">"{shoe}/boat"</span><span class="sxs-lookup"><span data-stu-id="81d30-173">"{shoe}/boat"</span></span>  
  
- <span data-ttu-id="81d30-174">"{shoe} / {划船} /bed/ {quilt}"</span><span class="sxs-lookup"><span data-stu-id="81d30-174">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
- <span data-ttu-id="81d30-175">"shoe / {划船}"</span><span class="sxs-lookup"><span data-stu-id="81d30-175">"shoe/{boat}"</span></span>  
  
- <span data-ttu-id="81d30-176">"shoe / {划船} /\*"</span><span class="sxs-lookup"><span data-stu-id="81d30-176">"shoe/{boat}/\*"</span></span>  
  
- <span data-ttu-id="81d30-177">"shoe/船？ x = 2"</span><span class="sxs-lookup"><span data-stu-id="81d30-177">"shoe/boat?x=2"</span></span>  
  
- <span data-ttu-id="81d30-178">"shoe / {划船}？ x = {平台}"</span><span class="sxs-lookup"><span data-stu-id="81d30-178">"shoe/{boat}?x={bed}"</span></span>  
  
- <span data-ttu-id="81d30-179">"shoe/{boat}?x={bed}&y=band"</span><span class="sxs-lookup"><span data-stu-id="81d30-179">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
- <span data-ttu-id="81d30-180">"？ x = {shoe}"</span><span class="sxs-lookup"><span data-stu-id="81d30-180">"?x={shoe}"</span></span>  
  
- <span data-ttu-id="81d30-181">"shoe?x=3&y={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-181">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="81d30-182">无效模板字符串的示例：</span><span class="sxs-lookup"><span data-stu-id="81d30-182">Examples of invalid template strings:</span></span>  
  
- <span data-ttu-id="81d30-183">"{shoe} / {SHOE} / x = 2"– 重复变量名。</span><span class="sxs-lookup"><span data-stu-id="81d30-183">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="81d30-184">"{shoe} /boat/？ bed = {shoe}"– 重复变量名。</span><span class="sxs-lookup"><span data-stu-id="81d30-184">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="81d30-185">"？ x = 2 (& x) = 3"– 查询字符串中的名称/值对必须是唯一的即使它们是文本。</span><span class="sxs-lookup"><span data-stu-id="81d30-185">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
- <span data-ttu-id="81d30-186">"？ x = 2 （& a)"– 查询字符串的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="81d30-186">"?x=2&" – Query string is malformed.</span></span>  
  
- <span data-ttu-id="81d30-187">"？ 2 和 x = {shoe}"– 查询字符串必须是名称/值对。</span><span class="sxs-lookup"><span data-stu-id="81d30-187">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
- <span data-ttu-id="81d30-188">"？ y = 2 & & X = 3"– 查询字符串必须是名称/值对，名称不能以开头 &。</span><span class="sxs-lookup"><span data-stu-id="81d30-188">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="81d30-189">复合路径段</span><span class="sxs-lookup"><span data-stu-id="81d30-189">Compound Path Segments</span></span>  
 <span data-ttu-id="81d30-190">复合路径段允许单个 URI 路径段包含多个变量，以及组合有文本的变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-190">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="81d30-191">下面这些示例都是有效的复合路径段：</span><span class="sxs-lookup"><span data-stu-id="81d30-191">The following are examples of valid compound path segments.</span></span>  
  
- <span data-ttu-id="81d30-192">/filename.{ext}/</span><span class="sxs-lookup"><span data-stu-id="81d30-192">/filename.{ext}/</span></span>  
  
- <span data-ttu-id="81d30-193">/{filename}.jpg/</span><span class="sxs-lookup"><span data-stu-id="81d30-193">/{filename}.jpg/</span></span>  
  
- <span data-ttu-id="81d30-194">/{filename}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="81d30-194">/{filename}.{ext}/</span></span>  
  
- <span data-ttu-id="81d30-195">/{a}.{b}someLiteral{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="81d30-195">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="81d30-196">下面这些示例都是无效的复合路径段：</span><span class="sxs-lookup"><span data-stu-id="81d30-196">The following are examples of invalid path segments.</span></span>  
  
- <span data-ttu-id="81d30-197">/{} -必须命名为变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-197">/{} - Variables must be named.</span></span>  
  
- <span data-ttu-id="81d30-198">/{shoe}{boat} - 必须用文本分隔变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-198">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="81d30-199">匹配和复合路径段</span><span class="sxs-lookup"><span data-stu-id="81d30-199">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="81d30-200">复合路径段允许定义在单个路径段内具有多个变量的 UriTemplate。</span><span class="sxs-lookup"><span data-stu-id="81d30-200">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="81d30-201">例如，在下面的模板字符串:"地址 / {state}。{city}"的同一段中定义两个变量 （state 和 city）。</span><span class="sxs-lookup"><span data-stu-id="81d30-201">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="81d30-202">此模板将匹配 URL 如`http://example.com/Washington.Redmond`，但它也会匹配的 URL，如`http://example.com/Washington.Redmond.Microsoft`。</span><span class="sxs-lookup"><span data-stu-id="81d30-202">This template would match a URL such as `http://example.com/Washington.Redmond` but it will also match an URL like `http://example.com/Washington.Redmond.Microsoft`.</span></span> <span data-ttu-id="81d30-203">在后一种情况下，状态变量将包含"Washington"，city 变量将包含"Redmond.Microsoft"。</span><span class="sxs-lookup"><span data-stu-id="81d30-203">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="81d30-204">这时，任何文本（“/”除外）都将与 {city} 变量相匹配。</span><span class="sxs-lookup"><span data-stu-id="81d30-204">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="81d30-205">如果你想将不匹配"额外的"文本模板，可将变量放在单独的模板段中，例如:"地址 / {state} / {city}。</span><span class="sxs-lookup"><span data-stu-id="81d30-205">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="81d30-206">命名通配符段</span><span class="sxs-lookup"><span data-stu-id="81d30-206">Named Wildcard Segments</span></span>  
 <span data-ttu-id="81d30-207">命名的通配符段是其变量名称开头的通配符字符的任何路径变量段\*。</span><span class="sxs-lookup"><span data-stu-id="81d30-207">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="81d30-208">下面的模板字符串包含一个名为“shoe”的命名通配符段。</span><span class="sxs-lookup"><span data-stu-id="81d30-208">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
```  
"literal/{*shoe}"  
```  
  
 <span data-ttu-id="81d30-209">通配符段必须遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="81d30-209">Wildcard segments must follow the following rules:</span></span>  
  
- <span data-ttu-id="81d30-210">每个模板字符串最多只能有一个命名通配符段。</span><span class="sxs-lookup"><span data-stu-id="81d30-210">There can be at most one named wildcard segment for each template string.</span></span>  
  
- <span data-ttu-id="81d30-211">命名通配符段必须位于路径中的最右段。</span><span class="sxs-lookup"><span data-stu-id="81d30-211">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
- <span data-ttu-id="81d30-212">命名通配符段不能与匿名通配符段共存于同一模板字符串中。</span><span class="sxs-lookup"><span data-stu-id="81d30-212">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
- <span data-ttu-id="81d30-213">命名通配符段的名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81d30-213">The name of a named wildcard segment must be unique.</span></span>  
  
- <span data-ttu-id="81d30-214">命名通配符段不能具有默认值。</span><span class="sxs-lookup"><span data-stu-id="81d30-214">Named wildcard segments cannot have default values.</span></span>  
  
- <span data-ttu-id="81d30-215">命名的通配符段不能以结尾"/"。</span><span class="sxs-lookup"><span data-stu-id="81d30-215">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="81d30-216">默认变量值</span><span class="sxs-lookup"><span data-stu-id="81d30-216">Default Variable Values</span></span>  
 <span data-ttu-id="81d30-217">通过默认变量值，可以在模板中指定变量的默认值。</span><span class="sxs-lookup"><span data-stu-id="81d30-217">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="81d30-218">默认变量可以用声明变量的大括号来指定，也可以指定为传递到 UriTemplate 构造函数的集合。</span><span class="sxs-lookup"><span data-stu-id="81d30-218">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="81d30-219">下面的模板演示用具有默认值的变量来指定 <xref:System.UriTemplate> 的两种方法。</span><span class="sxs-lookup"><span data-stu-id="81d30-219">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="81d30-220">此模板声明一个名为 `a`、默认值为 `1` 的变量和一个名为 `b`、默认值为 `5` 的变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-220">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81d30-221">仅允许路径段变量具有默认值。</span><span class="sxs-lookup"><span data-stu-id="81d30-221">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="81d30-222">不允许查询字符串变量、复合段变量和命名通配符变量具有默认值。</span><span class="sxs-lookup"><span data-stu-id="81d30-222">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="81d30-223">下面的代码演示在匹配候选 URI 时，如何处理默认变量值。</span><span class="sxs-lookup"><span data-stu-id="81d30-223">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> <span data-ttu-id="81d30-224">如 URI`http://localhost:8000///`与在前面的代码，但是列出模板不匹配的 URI，例如`http://localhost:8000/`does。</span><span class="sxs-lookup"><span data-stu-id="81d30-224">A URI such as `http://localhost:8000///` does not match the template listed in the preceding code, however a URI such as `http://localhost:8000/` does.</span></span>  
  
 <span data-ttu-id="81d30-225">下面的代码演示在使用模板创建 URI 时，如何处理默认变量值。</span><span class="sxs-lookup"><span data-stu-id="81d30-225">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
<span data-ttu-id="81d30-226">为变量提供默认值 `null` 时，有一些其他约束。</span><span class="sxs-lookup"><span data-stu-id="81d30-226">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="81d30-227">如果某个变量包含在模板字符串的最右段中，或者该段右侧的所有段都具有默认值 `null`，则该变量可以具有默认值 `null`。</span><span class="sxs-lookup"><span data-stu-id="81d30-227">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="81d30-228">下面是带有 `null` 默认值的有效模板字符串：</span><span class="sxs-lookup"><span data-stu-id="81d30-228">The following are valid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 <span data-ttu-id="81d30-229">以下是使用默认值的无效模板字符串`null`:</span><span class="sxs-lookup"><span data-stu-id="81d30-229">The following are invalid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a><span data-ttu-id="81d30-230">默认值和匹配</span><span class="sxs-lookup"><span data-stu-id="81d30-230">Default Values and Matching</span></span>  
 <span data-ttu-id="81d30-231">将候选 URI 与带有默认值的模板进行匹配时，如果候选 URI 中未指定值，则将在 <xref:System.UriTemplateMatch.BoundVariables%2A> 集合中放置默认值。</span><span class="sxs-lookup"><span data-stu-id="81d30-231">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="81d30-232">模板等效性</span><span class="sxs-lookup"><span data-stu-id="81d30-232">Template Equivalence</span></span>  
 <span data-ttu-id="81d30-233">两个模板被称为*结构等效*时所有模板的文本匹配且它们具有在相同的段中的变量。</span><span class="sxs-lookup"><span data-stu-id="81d30-233">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="81d30-234">例如，以下模板是结构等效的：</span><span class="sxs-lookup"><span data-stu-id="81d30-234">For example the following templates are structurally equivalent:</span></span>  
  
- <span data-ttu-id="81d30-235">/a/{var1}/b b/{var2}?x=1&y=2</span><span class="sxs-lookup"><span data-stu-id="81d30-235">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
- <span data-ttu-id="81d30-236">a/{x}/b%20b/{var1}?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-236">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
- <span data-ttu-id="81d30-237">a/{y}/B%20B/{z}/?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-237">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="81d30-238">在这里需注意一些事项：</span><span class="sxs-lookup"><span data-stu-id="81d30-238">A few things to notice:</span></span>  
  
- <span data-ttu-id="81d30-239">如果模板包含前导斜杠，则只忽略第一个。</span><span class="sxs-lookup"><span data-stu-id="81d30-239">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
- <span data-ttu-id="81d30-240">比较模板字符串以确定结构等效性时，变量名和路径段不区分大小写，查询字符串区分大小写。</span><span class="sxs-lookup"><span data-stu-id="81d30-240">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
- <span data-ttu-id="81d30-241">查询字符串不分次序。</span><span class="sxs-lookup"><span data-stu-id="81d30-241">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="81d30-242">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="81d30-242">UriTemplateTable</span></span>  
 <span data-ttu-id="81d30-243"><xref:System.UriTemplateTable> 类表示一个绑定到开发人员所选对象的 <xref:System.UriTemplate> 对象的关联表。</span><span class="sxs-lookup"><span data-stu-id="81d30-243">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="81d30-244">调用 <xref:System.UriTemplateTable> 之前，<xref:System.UriTemplate> 必须至少包含一个 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>。</span><span class="sxs-lookup"><span data-stu-id="81d30-244">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="81d30-245">在调用 <xref:System.UriTemplateTable> 之前，可以更改 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 的内容。</span><span class="sxs-lookup"><span data-stu-id="81d30-245">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="81d30-246">调用 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 时，会执行验证。</span><span class="sxs-lookup"><span data-stu-id="81d30-246">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="81d30-247">执行的验证的类型取决于传给 `allowMultiple` 的 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 参数的值。</span><span class="sxs-lookup"><span data-stu-id="81d30-247">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="81d30-248">如果在调用 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 时传入 `false`，则 <xref:System.UriTemplateTable> 将进行检查以确保表中无模板。</span><span class="sxs-lookup"><span data-stu-id="81d30-248">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="81d30-249">如果找到任何结构等效的模板，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="81d30-249">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="81d30-250">如果要确保只有一个模板与传入的 URI 匹配，可将此方法与 <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> 结合使用。</span><span class="sxs-lookup"><span data-stu-id="81d30-250">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="81d30-251">如果在调用 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> 时传入 `true`，则 <xref:System.UriTemplateTable> 允许 <xref:System.UriTemplateTable> 中包含多个结构等效的模板。</span><span class="sxs-lookup"><span data-stu-id="81d30-251">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="81d30-252">如果添加到 <xref:System.UriTemplate> 中的一组 <xref:System.UriTemplateTable> 对象包含查询字符串，则这些字符串不得有歧义。</span><span class="sxs-lookup"><span data-stu-id="81d30-252">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="81d30-253">可以使用相同的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="81d30-253">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81d30-254">尽管 <xref:System.UriTemplateTable> 允许使用除 HTTP 之外的方案的基址，但是将候选 URI 与模板匹配时，将忽略方案和端口号。</span><span class="sxs-lookup"><span data-stu-id="81d30-254">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="81d30-255">查询字符串多义性</span><span class="sxs-lookup"><span data-stu-id="81d30-255">Query String Ambiguity</span></span>  
 <span data-ttu-id="81d30-256">如果某个 URI 匹配多个模板，则共享等效路径的模板将包含歧义查询字符串。</span><span class="sxs-lookup"><span data-stu-id="81d30-256">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="81d30-257">以下几组查询字符串在其自身范围内无歧义：</span><span class="sxs-lookup"><span data-stu-id="81d30-257">The following sets of query strings are unambiguous within themselves:</span></span>  
  
- <span data-ttu-id="81d30-258">?x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-258">?x=1</span></span>  
  
- <span data-ttu-id="81d30-259">?x=2</span><span class="sxs-lookup"><span data-stu-id="81d30-259">?x=2</span></span>  
  
- <span data-ttu-id="81d30-260">?x=3</span><span class="sxs-lookup"><span data-stu-id="81d30-260">?x=3</span></span>  
  
- <span data-ttu-id="81d30-261">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-261">?x=1&y={var}</span></span>  
  
- <span data-ttu-id="81d30-262">?x=2&z={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-262">?x=2&z={var}</span></span>  
  
- <span data-ttu-id="81d30-263">?x=3</span><span class="sxs-lookup"><span data-stu-id="81d30-263">?x=3</span></span>  
  
- <span data-ttu-id="81d30-264">?x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-264">?x=1</span></span>  
  
- <span data-ttu-id="81d30-265">?</span><span class="sxs-lookup"><span data-stu-id="81d30-265">?</span></span>  
  
- <span data-ttu-id="81d30-266">?</span><span class="sxs-lookup"><span data-stu-id="81d30-266">?</span></span> <span data-ttu-id="81d30-267">x={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-267">x={var}</span></span>  
  
- <span data-ttu-id="81d30-268">?</span><span class="sxs-lookup"><span data-stu-id="81d30-268">?</span></span>  
  
- <span data-ttu-id="81d30-269">?m=get&c=rss</span><span class="sxs-lookup"><span data-stu-id="81d30-269">?m=get&c=rss</span></span>  
  
- <span data-ttu-id="81d30-270">?m=put&c=rss</span><span class="sxs-lookup"><span data-stu-id="81d30-270">?m=put&c=rss</span></span>  
  
- <span data-ttu-id="81d30-271">?m=get&c=atom</span><span class="sxs-lookup"><span data-stu-id="81d30-271">?m=get&c=atom</span></span>  
  
- <span data-ttu-id="81d30-272">?m=put&c=atom</span><span class="sxs-lookup"><span data-stu-id="81d30-272">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="81d30-273">以下几组查询字符串模板在其自身范围内有歧义：</span><span class="sxs-lookup"><span data-stu-id="81d30-273">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
- <span data-ttu-id="81d30-274">?x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-274">?x=1</span></span>  
  
- <span data-ttu-id="81d30-275">?x={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-275">?x={var}</span></span>  
  
 <span data-ttu-id="81d30-276">“x=1”- 与这两个模板都匹配。</span><span class="sxs-lookup"><span data-stu-id="81d30-276">"x=1" - Matches both templates.</span></span>  
  
- <span data-ttu-id="81d30-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-277">?x=1</span></span>  
  
- <span data-ttu-id="81d30-278">?y=2</span><span class="sxs-lookup"><span data-stu-id="81d30-278">?y=2</span></span>  
  
 <span data-ttu-id="81d30-279">“x=1&y=2”- 与这两个模板都匹配。</span><span class="sxs-lookup"><span data-stu-id="81d30-279">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="81d30-280">这是因为查询字符串包含的查询字符串变量可能比与之匹配的模板多。</span><span class="sxs-lookup"><span data-stu-id="81d30-280">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
- <span data-ttu-id="81d30-281">?x=1</span><span class="sxs-lookup"><span data-stu-id="81d30-281">?x=1</span></span>  
  
- <span data-ttu-id="81d30-282">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="81d30-282">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="81d30-283">“x=1&y=3”- 与这两个模板都匹配。</span><span class="sxs-lookup"><span data-stu-id="81d30-283">"x=1&y=3" matches both templates.</span></span>  
  
- <span data-ttu-id="81d30-284">?x=3&y=4</span><span class="sxs-lookup"><span data-stu-id="81d30-284">?x=3&y=4</span></span>  
  
- <span data-ttu-id="81d30-285">?x=3&z=5</span><span class="sxs-lookup"><span data-stu-id="81d30-285">?x=3&z=5</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81d30-286">作为 URI 路径或 <xref:System.UriTemplate> 路径段文本的组成部分时，字符 á 和 Á 视为不同的字符（但字符 a 和 A 视为相同的字符）。</span><span class="sxs-lookup"><span data-stu-id="81d30-286">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="81d30-287">作为 <xref:System.UriTemplate> {variableName} 或查询字符串的组成部分时，字符 á 和 Á 被视为相同的字符（字符 a 和 A 也视为相同的字符）。</span><span class="sxs-lookup"><span data-stu-id="81d30-287">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d30-288">请参阅</span><span class="sxs-lookup"><span data-stu-id="81d30-288">See Also</span></span>  
 [<span data-ttu-id="81d30-289">WCF Web HTTP 编程模型概述</span><span class="sxs-lookup"><span data-stu-id="81d30-289">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 [<span data-ttu-id="81d30-290">WCF Web HTTP 编程对象模型</span><span class="sxs-lookup"><span data-stu-id="81d30-290">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 [<span data-ttu-id="81d30-291">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="81d30-291">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)  
 [<span data-ttu-id="81d30-292">UriTemplate 表</span><span class="sxs-lookup"><span data-stu-id="81d30-292">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="81d30-293">UriTemplate 表调度程序</span><span class="sxs-lookup"><span data-stu-id="81d30-293">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
