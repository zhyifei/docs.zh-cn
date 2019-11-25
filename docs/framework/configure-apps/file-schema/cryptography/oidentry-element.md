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
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088551"
---
# <a name="oidentry-element"></a><span data-ttu-id="5289c-102">\<y > 元素</span><span class="sxs-lookup"><span data-stu-id="5289c-102">\<oidEntry> Element</span></span>
<span data-ttu-id="5289c-103">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="5289c-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

<span data-ttu-id="5289c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5289c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5289c-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5289c-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="5289c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<g s >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="5289c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="5289c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="5289c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="5289c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="5289c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5289c-109">语法</span><span class="sxs-lookup"><span data-stu-id="5289c-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5289c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5289c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5289c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5289c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5289c-112">特性</span><span class="sxs-lookup"><span data-stu-id="5289c-112">Attributes</span></span>  
  
|<span data-ttu-id="5289c-113">特性</span><span class="sxs-lookup"><span data-stu-id="5289c-113">Attribute</span></span>|<span data-ttu-id="5289c-114">描述</span><span class="sxs-lookup"><span data-stu-id="5289c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5289c-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="5289c-115">**OID**</span></span>|<span data-ttu-id="5289c-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="5289c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5289c-117">指定与您的类实现的算法相对应的第1个 OID。</span><span class="sxs-lookup"><span data-stu-id="5289c-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="5289c-118">**name**</span><span class="sxs-lookup"><span data-stu-id="5289c-118">**name**</span></span>|<span data-ttu-id="5289c-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="5289c-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="5289c-120">指定[\<y >](nameentry-element.md)标记中**name**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5289c-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5289c-121">子元素</span><span class="sxs-lookup"><span data-stu-id="5289c-121">Child Elements</span></span>  
 <span data-ttu-id="5289c-122">无。</span><span class="sxs-lookup"><span data-stu-id="5289c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5289c-123">父元素</span><span class="sxs-lookup"><span data-stu-id="5289c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5289c-124">元素</span><span class="sxs-lookup"><span data-stu-id="5289c-124">Element</span></span>|<span data-ttu-id="5289c-125">描述</span><span class="sxs-lookup"><span data-stu-id="5289c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5289c-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5289c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="5289c-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="5289c-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="5289c-128">包含 `cryptographySettings` 元素。</span><span class="sxs-lookup"><span data-stu-id="5289c-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="5289c-129">包含与类的 ASN 对象标识符（OID）映射。</span><span class="sxs-lookup"><span data-stu-id="5289c-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5289c-130">备注</span><span class="sxs-lookup"><span data-stu-id="5289c-130">Remarks</span></span>  
 <span data-ttu-id="5289c-131">ASN. 1 对象标识符以某些加密格式标识算法。</span><span class="sxs-lookup"><span data-stu-id="5289c-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="5289c-132">将对象标识符映射到要标识的算法的友好名称。</span><span class="sxs-lookup"><span data-stu-id="5289c-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5289c-133">示例</span><span class="sxs-lookup"><span data-stu-id="5289c-133">Example</span></span>  
 <span data-ttu-id="5289c-134">下面的示例演示如何使用 **\<y >** 元素将 160 RIPEMD 哈希算法的对象标识符映射到该哈希算法的实现。</span><span class="sxs-lookup"><span data-stu-id="5289c-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5289c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5289c-135">See also</span></span>

- [<span data-ttu-id="5289c-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="5289c-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5289c-137">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="5289c-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5289c-138">加密服务</span><span class="sxs-lookup"><span data-stu-id="5289c-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="5289c-139">配置加密类</span><span class="sxs-lookup"><span data-stu-id="5289c-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="5289c-140">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="5289c-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
