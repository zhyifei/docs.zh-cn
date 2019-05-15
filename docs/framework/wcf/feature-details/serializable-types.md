---
title: 可序列化类型
ms.date: 03/30/2017
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
ms.openlocfilehash: 0913d523e93505934b1cf231284e356baba5ded3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591673"
---
# <a name="serializable-types"></a><span data-ttu-id="2f897-102">可序列化类型</span><span class="sxs-lookup"><span data-stu-id="2f897-102">Serializable Types</span></span>
<span data-ttu-id="2f897-103">默认情况下，<xref:System.Runtime.Serialization.DataContractSerializer> 序列化所有公共可见类型。</span><span class="sxs-lookup"><span data-stu-id="2f897-103">By default, the <xref:System.Runtime.Serialization.DataContractSerializer> serializes all publicly visible types.</span></span> <span data-ttu-id="2f897-104">类型的所有公共读/写属性和字段均被序列化。</span><span class="sxs-lookup"><span data-stu-id="2f897-104">All public read/write properties and fields of the type are serialized.</span></span>  
  
 <span data-ttu-id="2f897-105">可以通过对类型和成员应用 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性来更改默认行为。当您拥有不受您控制因而无法对其进行修改以添加属性的类型时，此功能可能会十分有用。</span><span class="sxs-lookup"><span data-stu-id="2f897-105">You can change the default behavior by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the types and members This feature can be useful in situations in which you have types that are not under your control and cannot be modified to add attributes.</span></span> <span data-ttu-id="2f897-106"><xref:System.Runtime.Serialization.DataContractSerializer> 可识别这类“未标记”的类型。</span><span class="sxs-lookup"><span data-stu-id="2f897-106">The <xref:System.Runtime.Serialization.DataContractSerializer> recognizes such "unmarked" types.</span></span>  
  
## <a name="serialization-defaults"></a><span data-ttu-id="2f897-107">序列化默认设置</span><span class="sxs-lookup"><span data-stu-id="2f897-107">Serialization Defaults</span></span>  
 <span data-ttu-id="2f897-108">可以应用 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性以显式控制或自定义类型和成员的序列化。</span><span class="sxs-lookup"><span data-stu-id="2f897-108">You can apply the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to explicitly control or customize the serialization of types and members.</span></span> <span data-ttu-id="2f897-109">此外，还可以将这些属性应用于私有字段。</span><span class="sxs-lookup"><span data-stu-id="2f897-109">In addition, you can apply these attributes to private fields.</span></span> <span data-ttu-id="2f897-110">但是，即使未用这些属性进行标记的类型也会进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="2f897-110">However, even types that are not marked with these attributes are serialized and deserialized.</span></span> <span data-ttu-id="2f897-111">适用的规则和例外如下：</span><span class="sxs-lookup"><span data-stu-id="2f897-111">The following rules and exceptions apply:</span></span>  
  
- <span data-ttu-id="2f897-112"><xref:System.Runtime.Serialization.DataContractSerializer> 使用新创建的类型的默认属性从不带属性的类型推断数据协定。</span><span class="sxs-lookup"><span data-stu-id="2f897-112">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract from types without attributes using the default properties of the newly created types.</span></span>  
  
- <span data-ttu-id="2f897-113">除非对成员应用 `get` 属性 (Attribute)，否则所有公共字段以及具有公共 `set` 和 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> 方法的属性 (Property) 都会序列化。</span><span class="sxs-lookup"><span data-stu-id="2f897-113">All public fields, and properties with public `get` and `set` methods are serialized, unless you apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
- <span data-ttu-id="2f897-114">序列化语义与 <xref:System.Xml.Serialization.XmlSerializer> 的语义类似。</span><span class="sxs-lookup"><span data-stu-id="2f897-114">The serialization semantics are similar to those of the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
- <span data-ttu-id="2f897-115">在未标记的类型中，仅序列化具有不带参数的构造函数的公共类型。</span><span class="sxs-lookup"><span data-stu-id="2f897-115">In unmarked types, only public types with constructors that do not have parameters are serialized.</span></span> <span data-ttu-id="2f897-116">此规则的例外是用于 <xref:System.Runtime.Serialization.ExtensionDataObject> 接口的 <xref:System.Runtime.Serialization.IExtensibleDataObject>。</span><span class="sxs-lookup"><span data-stu-id="2f897-116">The exception to this rule is <xref:System.Runtime.Serialization.ExtensionDataObject> used with the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
- <span data-ttu-id="2f897-117">只读字段、没有 `get` 或 `set` 方法的属性以及具有内部或私有 `set` 或 `get` 方法的属性不会进行序列化。</span><span class="sxs-lookup"><span data-stu-id="2f897-117">Read-only fields, properties without a `get` or `set` method, and properties with internal or private `set` or `get` methods are not serialized.</span></span> <span data-ttu-id="2f897-118">此类属性会被忽略，但不会引发异常（get-only 集合的情况除外）。</span><span class="sxs-lookup"><span data-stu-id="2f897-118">Such properties are ignored and no exception is thrown, except in the case of get-only collections.</span></span>  
  
- <span data-ttu-id="2f897-119">会忽略 <xref:System.Xml.Serialization.XmlSerializer> 属性（如 `XmlElement`、`XmlAttribute`、`XmlIgnore`、`XmlInclude` 等）。</span><span class="sxs-lookup"><span data-stu-id="2f897-119"><xref:System.Xml.Serialization.XmlSerializer> attributes (such as `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude`, and so on) are ignored.</span></span>  
  
- <span data-ttu-id="2f897-120">如果未将 <xref:System.Runtime.Serialization.DataContractAttribute> 属性应用于某个给定类型，则序列化程序会忽略该类型中应用了 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性的所有成员。</span><span class="sxs-lookup"><span data-stu-id="2f897-120">If you do not apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a given type, the serializer ignores any member in that type to which the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute is applied.</span></span>  
  
- <span data-ttu-id="2f897-121">未使用 <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> 属性 (Attribute) 进行标记的类型中支持 <xref:System.Runtime.Serialization.DataContractAttribute> 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="2f897-121">The <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> property is supported in types not marked with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute.</span></span> <span data-ttu-id="2f897-122">这包括对未标记类型上的 <xref:System.Runtime.Serialization.KnownTypeAttribute> 属性 (Attribute) 的支持。</span><span class="sxs-lookup"><span data-stu-id="2f897-122">This includes support for the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute on unmarked types.</span></span>  
  
- <span data-ttu-id="2f897-123">若要使公共成员、属性 (Property) 或字段“退出”序列化过程，请向该成员应用 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> 属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="2f897-123">To "opt out" of the serialization process for public members, properties, or fields, apply the <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> attribute to that member.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="2f897-124">继承</span><span class="sxs-lookup"><span data-stu-id="2f897-124">Inheritance</span></span>  
 <span data-ttu-id="2f897-125">未标记类型（没有 <xref:System.Runtime.Serialization.DataContractAttribute> 属性的类型）可以从具有此属性的类型继承；但是反过来则不允许：具有该属性的类型不能从未标记类型继承。</span><span class="sxs-lookup"><span data-stu-id="2f897-125">Unmarked types (types without the <xref:System.Runtime.Serialization.DataContractAttribute> attribute) can inherit from types that do have this attribute; however, the reverse is not permitted: types with the attribute cannot inherit from unmarked types.</span></span> <span data-ttu-id="2f897-126">实施此规则主要是为了确保向后兼容早期版本的.NET Framework 中编写的代码。</span><span class="sxs-lookup"><span data-stu-id="2f897-126">This rule is enforced primarily to ensure backward compatibility with code written in earlier versions of .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f897-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f897-127">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="2f897-128">数据协定序列化程序支持的类型</span><span class="sxs-lookup"><span data-stu-id="2f897-128">Types Supported by the Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
