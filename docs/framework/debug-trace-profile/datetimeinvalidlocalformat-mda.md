---
title: dateTimeInvalidLocalFormat MDA
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54ce0f75ddfbf9f3b62917aa67f4d97140bbdc42
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153329"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="d0915-102">dateTimeInvalidLocalFormat MDA</span><span class="sxs-lookup"><span data-stu-id="d0915-102">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="d0915-103">使用只打算用于本地 <xref:System.DateTime> 实例的格式对存储为协调世界时 (UTC) 的 <xref:System.DateTime> 实例设置格式时，将激活 `dateTimeInvalidLocalFormat` MDA。</span><span class="sxs-lookup"><span data-stu-id="d0915-103">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="d0915-104">对于未指定的或默认的 <xref:System.DateTime> 实例，不激活此 MDA。</span><span class="sxs-lookup"><span data-stu-id="d0915-104">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="d0915-105">症状</span><span class="sxs-lookup"><span data-stu-id="d0915-105">Symptom</span></span>  
 <span data-ttu-id="d0915-106">应用程序使用本地格式手动序列化 UTC <xref:System.DateTime> 实例：</span><span class="sxs-lookup"><span data-stu-id="d0915-106">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="d0915-107">原因</span><span class="sxs-lookup"><span data-stu-id="d0915-107">Cause</span></span>  
 <span data-ttu-id="d0915-108"><xref:System.DateTime.ToString%2A?displayProperty=nameWithType> 方法的“z”格式包括本地时区偏移量，例如，“+10:00”表示悉尼时间。</span><span class="sxs-lookup"><span data-stu-id="d0915-108">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="d0915-109">就这一点而言，只有 <xref:System.DateTime> 值是本地时间时，它才会得出有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="d0915-109">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="d0915-110">如果该值是 UTC 时间，则 <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> 包括本地时区偏移量，但是不显示或调整时区说明符。</span><span class="sxs-lookup"><span data-stu-id="d0915-110">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="d0915-111">解决方法</span><span class="sxs-lookup"><span data-stu-id="d0915-111">Resolution</span></span>  
 <span data-ttu-id="d0915-112">应采用可表明 UTC <xref:System.DateTime> 实例为 UTC 时间的方式设置这些实例的格式。</span><span class="sxs-lookup"><span data-stu-id="d0915-112">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="d0915-113">对于 UTC 时间的格式，建议使用一个“Z”表示 UTC 时间：</span><span class="sxs-lookup"><span data-stu-id="d0915-113">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="d0915-114">还有一种利用正确序列化的 <xref:System.DateTime.Kind%2A> 属性序列化 <xref:System.DateTime> 的“o”格式，而不管实例是本地时间、UTC 时间还是未指定的时间：</span><span class="sxs-lookup"><span data-stu-id="d0915-114">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d0915-115">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="d0915-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="d0915-116">此 MDA 不影响运行时。</span><span class="sxs-lookup"><span data-stu-id="d0915-116">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d0915-117">输出</span><span class="sxs-lookup"><span data-stu-id="d0915-117">Output</span></span>  
 <span data-ttu-id="d0915-118">不存在作为此 MDA 激活的结果的特殊输出。但是，可使用调用堆栈确定激活此 MDA 的 <xref:System.DateTime.ToString%2A> 调用的位置。</span><span class="sxs-lookup"><span data-stu-id="d0915-118">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d0915-119">配置</span><span class="sxs-lookup"><span data-stu-id="d0915-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="d0915-120">示例</span><span class="sxs-lookup"><span data-stu-id="d0915-120">Example</span></span>  
 <span data-ttu-id="d0915-121">假设应用程序按以下方式使用 <xref:System.Xml.XmlConvert> 或 <xref:System.Data.DataSet> 类间接序列化 UTC <xref:System.DateTime> 值。</span><span class="sxs-lookup"><span data-stu-id="d0915-121">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="d0915-122"><xref:System.Xml.XmlConvert> 和 <xref:System.Data.DataSet> 序列化默认使用本地格式进行序列化。</span><span class="sxs-lookup"><span data-stu-id="d0915-122">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="d0915-123">序列化其他种类的 <xref:System.DateTime> 值（例如 UTC）需要其他选项。</span><span class="sxs-lookup"><span data-stu-id="d0915-123">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="d0915-124">对于此特定示例，将 `XmlDateTimeSerializationMode.RoundtripKind` 传递给 `XmlConvert` 上的 `ToString` 调用。</span><span class="sxs-lookup"><span data-stu-id="d0915-124">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="d0915-125">这会将数据序列化为 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="d0915-125">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="d0915-126">如果使用 <xref:System.Data.DataSet>，则将 <xref:System.Data.DataColumn> 对象上的 <xref:System.Data.DataColumn.DateTimeMode%2A> 属性设置为 <xref:System.Data.DataSetDateTime.Utc>。</span><span class="sxs-lookup"><span data-stu-id="d0915-126">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0915-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0915-127">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="d0915-128">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="d0915-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
