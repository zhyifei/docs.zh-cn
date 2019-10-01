---
title: <oidEntry> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: eed2a4d06906d2928be62aed20a75484c3eea946
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699770"
---
# <a name="oidentry-element"></a><span data-ttu-id="a035b-102">\<oidEntry > 元素</span><span class="sxs-lookup"><span data-stu-id="a035b-102">\<oidEntry> Element</span></span>
<span data-ttu-id="a035b-103">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="a035b-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
[<span data-ttu-id="a035b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a035b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a035b-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a035b-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="a035b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="a035b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="a035b-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="a035b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="a035b-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="a035b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a035b-109">语法</span><span class="sxs-lookup"><span data-stu-id="a035b-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a035b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a035b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a035b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a035b-112">特性</span><span class="sxs-lookup"><span data-stu-id="a035b-112">Attributes</span></span>  
  
|<span data-ttu-id="a035b-113">特性</span><span class="sxs-lookup"><span data-stu-id="a035b-113">Attribute</span></span>|<span data-ttu-id="a035b-114">描述</span><span class="sxs-lookup"><span data-stu-id="a035b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a035b-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="a035b-115">**OID**</span></span>|<span data-ttu-id="a035b-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a035b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="a035b-117">指定与您的类实现的算法相对应的第1个 OID。</span><span class="sxs-lookup"><span data-stu-id="a035b-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="a035b-118">**name**</span><span class="sxs-lookup"><span data-stu-id="a035b-118">**name**</span></span>|<span data-ttu-id="a035b-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a035b-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="a035b-120">指定[\<nameEntry >](nameentry-element.md)标记中**name**属性的值。</span><span class="sxs-lookup"><span data-stu-id="a035b-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a035b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="a035b-121">Child Elements</span></span>  
 <span data-ttu-id="a035b-122">无。</span><span class="sxs-lookup"><span data-stu-id="a035b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a035b-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a035b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a035b-124">元素</span><span class="sxs-lookup"><span data-stu-id="a035b-124">Element</span></span>|<span data-ttu-id="a035b-125">描述</span><span class="sxs-lookup"><span data-stu-id="a035b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a035b-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a035b-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="a035b-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="a035b-128">`cryptographySettings`包含元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="a035b-129">包含与类的 ASN 对象标识符（OID）映射。</span><span class="sxs-lookup"><span data-stu-id="a035b-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a035b-130">备注</span><span class="sxs-lookup"><span data-stu-id="a035b-130">Remarks</span></span>  
 <span data-ttu-id="a035b-131">ASN. 1 对象标识符以某些加密格式标识算法。</span><span class="sxs-lookup"><span data-stu-id="a035b-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="a035b-132">将对象标识符映射到要标识的算法的友好名称。</span><span class="sxs-lookup"><span data-stu-id="a035b-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a035b-133">示例</span><span class="sxs-lookup"><span data-stu-id="a035b-133">Example</span></span>  
 <span data-ttu-id="a035b-134">下面的示例演示如何使用 **\<oidEntry >** 元素将 160 RIPEMD 哈希算法的对象标识符映射到该哈希算法的实现。</span><span class="sxs-lookup"><span data-stu-id="a035b-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a035b-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a035b-135">See also</span></span>

- [<span data-ttu-id="a035b-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a035b-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a035b-137">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="a035b-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a035b-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a035b-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a035b-139">配置加密类</span><span class="sxs-lookup"><span data-stu-id="a035b-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="a035b-140">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="a035b-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
