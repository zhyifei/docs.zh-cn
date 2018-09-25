---
title: '&lt;oidEntry&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c5be6ef95693f274e5cb2002e5642d5e58a7661a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082063"
---
# <a name="ltoidentrygt-element"></a><span data-ttu-id="1860d-102">&lt;oidEntry&gt;元素</span><span class="sxs-lookup"><span data-stu-id="1860d-102">&lt;oidEntry&gt; Element</span></span>
<span data-ttu-id="1860d-103">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="1860d-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="1860d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1860d-104">\<configuration></span></span>  
<span data-ttu-id="1860d-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="1860d-105">\<mscorlib></span></span>  
<span data-ttu-id="1860d-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="1860d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="1860d-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="1860d-107">\<oidMap></span></span>  
<span data-ttu-id="1860d-108">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="1860d-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1860d-109">语法</span><span class="sxs-lookup"><span data-stu-id="1860d-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1860d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1860d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1860d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1860d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1860d-112">特性</span><span class="sxs-lookup"><span data-stu-id="1860d-112">Attributes</span></span>  
  
|<span data-ttu-id="1860d-113">特性</span><span class="sxs-lookup"><span data-stu-id="1860d-113">Attribute</span></span>|<span data-ttu-id="1860d-114">描述</span><span class="sxs-lookup"><span data-stu-id="1860d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1860d-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="1860d-115">**OID**</span></span>|<span data-ttu-id="1860d-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1860d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="1860d-117">指定的 ASN.1 OID 对应于您的类所实现的算法。</span><span class="sxs-lookup"><span data-stu-id="1860d-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="1860d-118">**name**</span><span class="sxs-lookup"><span data-stu-id="1860d-118">**name**</span></span>|<span data-ttu-id="1860d-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1860d-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="1860d-120">指定的值**名称**属性中[ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)标记。</span><span class="sxs-lookup"><span data-stu-id="1860d-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1860d-121">子元素</span><span class="sxs-lookup"><span data-stu-id="1860d-121">Child Elements</span></span>  
 <span data-ttu-id="1860d-122">无。</span><span class="sxs-lookup"><span data-stu-id="1860d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1860d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1860d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1860d-124">元素</span><span class="sxs-lookup"><span data-stu-id="1860d-124">Element</span></span>|<span data-ttu-id="1860d-125">描述</span><span class="sxs-lookup"><span data-stu-id="1860d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1860d-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1860d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="1860d-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="1860d-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="1860d-128">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="1860d-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="1860d-129">包含类的 ASN.1 对象标识符 (OID) 映射。</span><span class="sxs-lookup"><span data-stu-id="1860d-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1860d-130">备注</span><span class="sxs-lookup"><span data-stu-id="1860d-130">Remarks</span></span>  
 <span data-ttu-id="1860d-131">ASN.1 对象标识符标识中某些加密格式的算法。</span><span class="sxs-lookup"><span data-stu-id="1860d-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="1860d-132">将对象标识符映射到你想要识别的算法的友好名称。</span><span class="sxs-lookup"><span data-stu-id="1860d-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1860d-133">示例</span><span class="sxs-lookup"><span data-stu-id="1860d-133">Example</span></span>  
 <span data-ttu-id="1860d-134">下面的示例演示如何使用 **\<oidEntry >** 元素将 RIPEMD-160 哈希算法的对象标识符映射到该哈希算法的实现。</span><span class="sxs-lookup"><span data-stu-id="1860d-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1860d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="1860d-135">See Also</span></span>  
 [<span data-ttu-id="1860d-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="1860d-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1860d-137">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="1860d-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="1860d-138">加密服务</span><span class="sxs-lookup"><span data-stu-id="1860d-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="1860d-139">配置加密类</span><span class="sxs-lookup"><span data-stu-id="1860d-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="1860d-140">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="1860d-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
