---
title: "版本容错序列化"
ms.date: 08/08/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- version tolerant serialization
- serialization, custom serialization
- serialization, version tolerant
- serialization, controlling
- versions and serialization
- BinaryFormatter class, samples
- serialization, attributes
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 90f2b1e73a24b0f732eaba4422faa9a1dcc15135
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="version-tolerant-serialization"></a><span data-ttu-id="e7eec-102">版本容错序列化</span><span class="sxs-lookup"><span data-stu-id="e7eec-102">Version tolerant serialization</span></span>
<span data-ttu-id="e7eec-103">在 .NET Framework 1.0 和 1.1 版本中，创建可从应用程序的一个版本重用至下一个版本的可序列化类型时会产生问题。</span><span class="sxs-lookup"><span data-stu-id="e7eec-103">In version 1.0 and 1.1 of the .NET Framework, creating serializable types that would be reusable from one version of an application to the next was problematic.</span></span> <span data-ttu-id="e7eec-104">如果通过添加额外字段来修改类型，则会出现以下问题：</span><span class="sxs-lookup"><span data-stu-id="e7eec-104">If a type was modified by adding extra fields, the following problems would occur:</span></span>  
  
-   <span data-ttu-id="e7eec-105">要求应用程序的较旧版本反序列化旧类型的新版本时，会引发异常。</span><span class="sxs-lookup"><span data-stu-id="e7eec-105">Older versions of an application would throw exceptions when asked to deserialize new versions of the old type.</span></span>  
  
-   <span data-ttu-id="e7eec-106">应用程序的较新版本反序列化缺少数据的类型的较旧版本时，会引发异常。</span><span class="sxs-lookup"><span data-stu-id="e7eec-106">Newer versions of an application would throw exceptions when deserializing older versions of a type with missing data.</span></span>  
  
 <span data-ttu-id="e7eec-107">版本容错序列化 (VTS) 是 .NET Framework 2.0 中引入的一组功能，它使得修改可序列化类型随着时间推移而变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="e7eec-107">Version Tolerant Serialization (VTS) is a set of features introduced in .NET Framework 2.0 that makes it easier, over time, to modify serializable types.</span></span> <span data-ttu-id="e7eec-108">VTS 功能尤其是为应用了 <xref:System.SerializableAttribute> 特性的类（包括泛型类型）而启用的。</span><span class="sxs-lookup"><span data-stu-id="e7eec-108">Specifically, the VTS features are enabled for classes to which the <xref:System.SerializableAttribute> attribute has been applied, including generic types.</span></span> <span data-ttu-id="e7eec-109">VTS 允许向这些类添加新字段，而不破坏与该类型其他版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-109">VTS makes it possible to add new fields to those classes without breaking compatibility with other versions of the type.</span></span> <span data-ttu-id="e7eec-110">有关可用的示例应用程序，请参阅[版本容错序列化技术示例](../../../docs/standard/serialization/version-tolerant-serialization-technology-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e7eec-110">For a working sample application, see [Version Tolerant Serialization Technology Sample](../../../docs/standard/serialization/version-tolerant-serialization-technology-sample.md).</span></span>  
  
 <span data-ttu-id="e7eec-111">当使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 时，将启用 VTS 功能。</span><span class="sxs-lookup"><span data-stu-id="e7eec-111">The VTS features are enabled when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="e7eec-112">此外，当使用 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 时，也会启用除外来数据容错以外的其他所有功能。</span><span class="sxs-lookup"><span data-stu-id="e7eec-112">Additionally, all features except extraneous data tolerance are also enabled when using the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="e7eec-113">有关将这些类用于序列化的详细信息，请参见[二进制序列化](binary-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="e7eec-113">For more information about using these classes for serialization, see [Binary Serialization](binary-serialization.md).</span></span>  
  
[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a><span data-ttu-id="e7eec-114">功能列表</span><span class="sxs-lookup"><span data-stu-id="e7eec-114">Feature list</span></span>  
 <span data-ttu-id="e7eec-115">功能集包括：</span><span class="sxs-lookup"><span data-stu-id="e7eec-115">The set of features includes the following:</span></span>  
  
-   <span data-ttu-id="e7eec-116">外来或意外数据容错功能。</span><span class="sxs-lookup"><span data-stu-id="e7eec-116">Tolerance of extraneous or unexpected data.</span></span> <span data-ttu-id="e7eec-117">该功能允许类型的较新版本将数据发送至较旧版本。</span><span class="sxs-lookup"><span data-stu-id="e7eec-117">This enables newer versions of the type to send data to older versions.</span></span>  
  
-   <span data-ttu-id="e7eec-118">缺少可选数据容错功能。</span><span class="sxs-lookup"><span data-stu-id="e7eec-118">Tolerance of missing optional data.</span></span> <span data-ttu-id="e7eec-119">该功能允许较旧版本将数据发送至较新版本。</span><span class="sxs-lookup"><span data-stu-id="e7eec-119">This enables older versions to send data to newer versions.</span></span>  
  
-   <span data-ttu-id="e7eec-120">序列化回调。</span><span class="sxs-lookup"><span data-stu-id="e7eec-120">Serialization callbacks.</span></span> <span data-ttu-id="e7eec-121">该功能在缺少数据的情况下启用智能默认值设置。</span><span class="sxs-lookup"><span data-stu-id="e7eec-121">This enables intelligent default value setting in cases where data is missing.</span></span>  
  
 <span data-ttu-id="e7eec-122">此外，添加了新的可选字段时还有声明功能。</span><span class="sxs-lookup"><span data-stu-id="e7eec-122">In addition, there is a feature for declaring when a new optional field has been added.</span></span> <span data-ttu-id="e7eec-123">这是 <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> 特性的 <xref:System.Runtime.Serialization.OptionalFieldAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-123">This is the <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> property of the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute.</span></span>  
  
 <span data-ttu-id="e7eec-124">以上功能在下面的内容中详述。</span><span class="sxs-lookup"><span data-stu-id="e7eec-124">These features are discussed in greater detail below.</span></span>  
  
## <a name="tolerance-of-extraneous-or-unexpected-data"></a><span data-ttu-id="e7eec-125">外来或意外数据容错功能</span><span class="sxs-lookup"><span data-stu-id="e7eec-125">Tolerance of extraneous or unexpected data</span></span>  
 <span data-ttu-id="e7eec-126">过去在反序列化时，任何外来或意外数据都会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="e7eec-126">In the past, during deserialization, any extraneous or unexpected data caused exceptions to be thrown.</span></span> <span data-ttu-id="e7eec-127">有了 VTS 后，在相同情况下会忽略所有外来或意外数据，而不会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="e7eec-127">With VTS, in the same situation, any extraneous or unexpected data is ignored instead of causing exceptions to be thrown.</span></span> <span data-ttu-id="e7eec-128">这就使得使用类型的较新版本（即包含更多字段的版本）的应用程序可以将信息发送至需要使用同一类型的较旧版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7eec-128">This enables applications that use newer versions of a type (that is, a version that includes more fields) to send information to applications that expect older versions of the same type.</span></span>  
  
 <span data-ttu-id="e7eec-129">在下面的示例中，当较旧版本的应用程序反序列化较新版本时，将忽略 `CountryField` 类 2.0 版的 `Address` 中包含的额外数据。</span><span class="sxs-lookup"><span data-stu-id="e7eec-129">In the following example, the extra data contained in the `CountryField` of version 2.0 of the `Address` class is ignored when an older application deserializes the newer version.</span></span>  
  
```csharp  
// Version 1 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
}  
// Version 2.0 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    // The older application ignores this data.  
    public string CountryField;  
}  
```  
  
```vb  
' Version 1 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
End Class  
  
' Version 2.0 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    ' The older application ignores this data.  
    Public CountryField As String  
End Class  
```  
  
## <a name="tolerance-of-missing-data"></a><span data-ttu-id="e7eec-130">丢失数据容错功能</span><span class="sxs-lookup"><span data-stu-id="e7eec-130">Tolerance of missing data</span></span>  
 <span data-ttu-id="e7eec-131">通过将 <xref:System.Runtime.Serialization.OptionalFieldAttribute> 特性应用于字段，可以将字段标记为可选。</span><span class="sxs-lookup"><span data-stu-id="e7eec-131">Fields can be marked as optional by applying the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to them.</span></span> <span data-ttu-id="e7eec-132">在反序列化期间，如果缺少可选的数据，序列化引擎会忽略这一缺失且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="e7eec-132">During deserialization, if the optional data is missing, the serialization engine ignores the absence and does not throw an exception.</span></span> <span data-ttu-id="e7eec-133">因此，需要使用类型的较旧版本的应用程序可以将数据发送至需要使用同一类型的较新版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7eec-133">Thus, applications that expect older versions of a type can send data to applications that expect newer versions of the same type.</span></span>  
  
 <span data-ttu-id="e7eec-134">下面的示例显示的是 `Address` 类的 2.0 版，其 `CountryField` 字段标记为可选。</span><span class="sxs-lookup"><span data-stu-id="e7eec-134">The following example shows version 2.0 of the `Address` class with the `CountryField` field marked as optional.</span></span> <span data-ttu-id="e7eec-135">如果较旧版本的应用程序将版本 1 发送至需要使用 2.0 版的较新版本的应用程序，则会忽略数据缺失。</span><span class="sxs-lookup"><span data-stu-id="e7eec-135">If an older application sends version 1 to a newer application that expects version 2.0, the absence of the data is ignored.</span></span>  
  
```csharp  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
  
    [OptionalField]  
    public string CountryField;  
}  
```  
  
```vb  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
  
    <OptionalField> _  
    Public CountryField As String  
End Class  
```  
  
## <a name="serialization-callbacks"></a><span data-ttu-id="e7eec-136">序列化回调</span><span class="sxs-lookup"><span data-stu-id="e7eec-136">Serialization callbacks</span></span>  
 <span data-ttu-id="e7eec-137">序列化回调是一种机制，它在序列化/反序列化过程中的四个点提供挂钩。</span><span class="sxs-lookup"><span data-stu-id="e7eec-137">Serialization callbacks are a mechanism that provides hooks into the serialization/deserialization process at four points.</span></span>  
  
|<span data-ttu-id="e7eec-138">特性</span><span class="sxs-lookup"><span data-stu-id="e7eec-138">Attribute</span></span>|<span data-ttu-id="e7eec-139">调用关联的方法时</span><span class="sxs-lookup"><span data-stu-id="e7eec-139">When the Associated Method is Called</span></span>|<span data-ttu-id="e7eec-140">典型用法</span><span class="sxs-lookup"><span data-stu-id="e7eec-140">Typical Use</span></span>|  
|---------------|------------------------------------------|-----------------|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="e7eec-141">反序列化之前。*</span><span class="sxs-lookup"><span data-stu-id="e7eec-141">Before deserialization.*</span></span>|<span data-ttu-id="e7eec-142">初始化可选字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="e7eec-142">Initialize default values for optional fields.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="e7eec-143">反序列化之后。</span><span class="sxs-lookup"><span data-stu-id="e7eec-143">After deserialization.</span></span>|<span data-ttu-id="e7eec-144">根据其他字段的内容修改可选字段值。</span><span class="sxs-lookup"><span data-stu-id="e7eec-144">Fix optional field values based on contents of other fields.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="e7eec-145">序列化之前。</span><span class="sxs-lookup"><span data-stu-id="e7eec-145">Before serialization.</span></span>|<span data-ttu-id="e7eec-146">准备序列化。</span><span class="sxs-lookup"><span data-stu-id="e7eec-146">Prepare for serialization.</span></span> <span data-ttu-id="e7eec-147">例如，创建可选数据结构。</span><span class="sxs-lookup"><span data-stu-id="e7eec-147">For example, create optional data structures.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="e7eec-148">序列化之后。</span><span class="sxs-lookup"><span data-stu-id="e7eec-148">After serialization.</span></span>|<span data-ttu-id="e7eec-149">记录序列化事件。</span><span class="sxs-lookup"><span data-stu-id="e7eec-149">Log serialization events.</span></span>|  
  
 <span data-ttu-id="e7eec-150">\* 如果有反序列化构造函数，则在该构造函数之前调用此回调。</span><span class="sxs-lookup"><span data-stu-id="e7eec-150">\* This callback is invoked before the deserialization constructor, if one is present.</span></span>  
  
### <a name="using-callbacks"></a><span data-ttu-id="e7eec-151">使用回调</span><span class="sxs-lookup"><span data-stu-id="e7eec-151">Using callbacks</span></span>  
 <span data-ttu-id="e7eec-152">要使用回调，请将相应的特性应用于接受 <xref:System.Runtime.Serialization.StreamingContext> 参数的方法。</span><span class="sxs-lookup"><span data-stu-id="e7eec-152">To use callbacks, apply the appropriate attribute to a method that accepts a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span> <span data-ttu-id="e7eec-153">每个类只有一个方法可以用其中每个特性进行标记。</span><span class="sxs-lookup"><span data-stu-id="e7eec-153">Only one method per class can be marked with each of these attributes.</span></span> <span data-ttu-id="e7eec-154">例如：</span><span class="sxs-lookup"><span data-stu-id="e7eec-154">For example:</span></span>  
  
```csharp  
[OnDeserializing]  
private void SetCountryRegionDefault(StreamingContext sc)  
{  
    CountryField = "Japan";  
}  
```  
  
```vb  
<OnDeserializing>  
Private Sub SetCountryRegionDefault(StreamingContext sc)  
    CountryField = "Japan";  
End Sub  
```  
  
 <span data-ttu-id="e7eec-155">这些方法旨在用于版本管理。</span><span class="sxs-lookup"><span data-stu-id="e7eec-155">The intended use of these methods is for versioning.</span></span> <span data-ttu-id="e7eec-156">在反序列化期间，如果可选字段缺少数据，则可能无法正确初始化该字段。</span><span class="sxs-lookup"><span data-stu-id="e7eec-156">During deserialization, an optional field may not be correctly initialized if the data for the field is missing.</span></span> <span data-ttu-id="e7eec-157">若要更正这一情况，可以创建分配正确值的方法，然后将 OnDeserializingAttribute 或 OnDeserializedAttribute 特性应用于该方法。</span><span class="sxs-lookup"><span data-stu-id="e7eec-157">This can be corrected by creating the method that assigns the correct value, then applying either the **OnDeserializingAttribute** or **OnDeserializedAttribute** attribute to the method.</span></span>  
  
 <span data-ttu-id="e7eec-158">下面的示例演示类型上下文中的方法。</span><span class="sxs-lookup"><span data-stu-id="e7eec-158">The following example shows the method in the context of a type.</span></span> <span data-ttu-id="e7eec-159">如果应用程序的较旧版本将 `Address` 类的实例发送至该应用程序的较新版本，将会丢失 `CountryField` 字段数据。</span><span class="sxs-lookup"><span data-stu-id="e7eec-159">If an earlier version of an application sends an instance of the `Address` class to a later version of the application, the `CountryField` field data will be missing.</span></span> <span data-ttu-id="e7eec-160">但是反序列化之后，会将字段设置为默认值“Japan”。</span><span class="sxs-lookup"><span data-stu-id="e7eec-160">But after deserialization, the field will be set to a default value "Japan."</span></span>  
  
```csharp  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    [OptionalField]  
    public string CountryField;  
  
    [OnDeserializing]  
    private void SetCountryRegionDefault (StreamingContext sc)  
    {  
        CountryField = "Japan";  
    }  
}  
```  
  
```vb  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    <OptionalField> _  
    Public CountryField As String  
  
    <OnDeserializing> _  
    Private Sub SetCountryRegionDefault(StreamingContext sc)  
        CountryField = "Japan";  
    End Sub  
End Class  
```  
  
## <a name="the-versionadded-property"></a><span data-ttu-id="e7eec-161">VersionAdded 属性</span><span class="sxs-lookup"><span data-stu-id="e7eec-161">The VersionAdded property</span></span>  
 <span data-ttu-id="e7eec-162">OptionalFieldAttribute 具有 VersionAdded 属性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-162">The **OptionalFieldAttribute** has the **VersionAdded** property.</span></span> <span data-ttu-id="e7eec-163">在 .NET Framework 2.0 版中，未使用这一属性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-163">In version 2.0 of the .NET Framework, this isn't used.</span></span> <span data-ttu-id="e7eec-164">然而，为确保类型与将来的序列化引擎兼容，需要正确设置此属性，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="e7eec-164">However, it's important to set this property correctly to ensure that the type will be compatible with future serialization engines.</span></span>  
  
 <span data-ttu-id="e7eec-165">该属性指示向给定字段添加了类型的哪个版本。</span><span class="sxs-lookup"><span data-stu-id="e7eec-165">The property indicates which version of a type a given field has been added.</span></span> <span data-ttu-id="e7eec-166">每次修改类型时，版本应该正好增加一（从 2 开始），如下例所示：</span><span class="sxs-lookup"><span data-stu-id="e7eec-166">It should be incremented by exactly one (starting at 2) every time the type is modified, as shown in the following example:</span></span>  
  
```csharp  
// Version 1.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
}  
  
// Version 2.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
  
    [OptionalField(VersionAdded = 2)]  
    public string NickName;  
    [OptionalField(VersionAdded = 2)]  
    public DateTime BirthDate;  
}  
  
// Version 3.0  
[Serializable]  
public class Person  
{  
    public string FullName;  
  
    [OptionalField(VersionAdded=2)]  
    public string NickName;  
    [OptionalField(VersionAdded=2)]  
    public DateTime BirthDate;  
  
    [OptionalField(VersionAdded=3)]  
    public int Weight;  
}  
```  
  
```vb  
' Version 1.0  
<Serializable> _  
Public Class Person  
    Public FullName  
End Class  
  
' Version 2.0  
<Serializable> _  
Public Class Person  
    Public FullName As String  
  
    <OptionalField(VersionAdded := 2)> _  
    Public NickName As String  
    <OptionalField(VersionAdded := 2)> _  
    Public BirthDate As DateTime  
End Class  
  
' Version 3.0  
<Serializable> _  
Public Class Person  
    Public FullName As String  
  
    <OptionalField(VersionAdded := 2)> _  
    Public NickName As String  
    <OptionalField(VersionAdded := 2)> _  
    Public BirthDate As DateTime  
  
    <OptionalField(VersionAdded := 3)> _  
    Public Weight As Integer  
End Class  
```  
  
## <a name="serializationbinder"></a><span data-ttu-id="e7eec-167">SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="e7eec-167">SerializationBinder</span></span>  
 <span data-ttu-id="e7eec-168">由于服务器和客户端要求使用不同的类版本，因此，有些用户可能需要控制要序列化和反序列化哪些类。</span><span class="sxs-lookup"><span data-stu-id="e7eec-168">Some users may need to control which class to serialize and deserialize because a different version of the class is required on the server and client.</span></span> <span data-ttu-id="e7eec-169"><xref:System.Runtime.Serialization.SerializationBinder> 是抽象类，用于控制在序列化和反序列化期间使用的实际类型。</span><span class="sxs-lookup"><span data-stu-id="e7eec-169"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span>  <span data-ttu-id="e7eec-170">若要使用此类，请从 <xref:System.Runtime.Serialization.SerializationBinder> 派生类，并重写 <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> 和 <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7eec-170">To use this class, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> methods.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="e7eec-171">[控制序列化和反序列化使用 SerializationBinder](../../../docs/framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md)。</span><span class="sxs-lookup"><span data-stu-id="e7eec-171"> [Controlling Serialization and Deserialization with SerializationBinder](../../../docs/framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="e7eec-172">最佳实践</span><span class="sxs-lookup"><span data-stu-id="e7eec-172">Best practices</span></span>  
 <span data-ttu-id="e7eec-173">要确保版本管理行为正确，修改类型版本时请遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="e7eec-173">To ensure proper versioning behavior, follow these rules when modifying a type from version to version:</span></span>  
  
-   <span data-ttu-id="e7eec-174">切勿移除已序列化的字段。</span><span class="sxs-lookup"><span data-stu-id="e7eec-174">Never remove a serialized field.</span></span>  
  
-   <span data-ttu-id="e7eec-175">如果未在以前版本中将 <xref:System.NonSerializedAttribute> 特性应用于某个字段，则切勿将该特性应用于该字段。</span><span class="sxs-lookup"><span data-stu-id="e7eec-175">Never apply the <xref:System.NonSerializedAttribute> attribute to a field if the attribute was not applied to the field in the previous version.</span></span>  
  
-   <span data-ttu-id="e7eec-176">切勿更改已序列化字段的名称或类型。</span><span class="sxs-lookup"><span data-stu-id="e7eec-176">Never change the name or the type of a serialized field.</span></span>  
  
-   <span data-ttu-id="e7eec-177">添加新的已序列化字段时，请应用 OptionalFieldAttribute 特性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-177">When adding a new serialized field, apply the **OptionalFieldAttribute** attribute.</span></span>  
  
-   <span data-ttu-id="e7eec-178">从字段（在以前版本中不可序列化）中移除 NonSerializedAttribute 特性时，请应用 OptionalFieldAttribute 特性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-178">When removing a **NonSerializedAttribute** attribute from a field (that was not serializable in a previous version), apply the **OptionalFieldAttribute** attribute.</span></span>  
  
-   <span data-ttu-id="e7eec-179">对于所有可选字段，除非可接受 0 或 null 作为默认值，否则请使用序列化回调设置有意义的默认值。</span><span class="sxs-lookup"><span data-stu-id="e7eec-179">For all optional fields, set meaningful defaults using the serialization callbacks unless 0 or **null** as defaults are acceptable.</span></span>  
  
 <span data-ttu-id="e7eec-180">要确保类型与将来的序列化引擎兼容，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="e7eec-180">To ensure that a type will be compatible with future serialization engines, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="e7eec-181">始终正确设置 OptionalFieldAttribute 特性上的 VersionAdded 属性。</span><span class="sxs-lookup"><span data-stu-id="e7eec-181">Always set the **VersionAdded** property on the **OptionalFieldAttribute** attribute correctly.</span></span>  
  
-   <span data-ttu-id="e7eec-182">避免版本管理分支。</span><span class="sxs-lookup"><span data-stu-id="e7eec-182">Avoid branched versioning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7eec-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7eec-183">See also</span></span>  
 <xref:System.SerializableAttribute>  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>  
 <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>  
 <xref:System.Runtime.Serialization.OptionalFieldAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 <xref:System.NonSerializedAttribute>  
 [<span data-ttu-id="e7eec-184">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="e7eec-184">Binary Serialization</span></span>](binary-serialization.md)
