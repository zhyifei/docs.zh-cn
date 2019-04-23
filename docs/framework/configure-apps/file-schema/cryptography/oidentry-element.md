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
ms.openlocfilehash: c686d2b99ad66aec753a356b09fa3c7151193808
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219338"
---
# <a name="oidentry-element"></a><span data-ttu-id="b2359-102">\<oidEntry > 元素</span><span class="sxs-lookup"><span data-stu-id="b2359-102">\<oidEntry> Element</span></span>
<span data-ttu-id="b2359-103">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="b2359-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="b2359-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2359-104">\<configuration></span></span>  
<span data-ttu-id="b2359-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="b2359-105">\<mscorlib></span></span>  
<span data-ttu-id="b2359-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="b2359-106">\<cryptographySettings></span></span>  
<span data-ttu-id="b2359-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="b2359-107">\<oidMap></span></span>  
<span data-ttu-id="b2359-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="b2359-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2359-109">语法</span><span class="sxs-lookup"><span data-stu-id="b2359-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2359-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b2359-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2359-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b2359-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2359-112">特性</span><span class="sxs-lookup"><span data-stu-id="b2359-112">Attributes</span></span>  
  
|<span data-ttu-id="b2359-113">特性</span><span class="sxs-lookup"><span data-stu-id="b2359-113">Attribute</span></span>|<span data-ttu-id="b2359-114">描述</span><span class="sxs-lookup"><span data-stu-id="b2359-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2359-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="b2359-115">**OID**</span></span>|<span data-ttu-id="b2359-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b2359-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b2359-117">指定的 ASN.1 OID 对应于您的类所实现的算法。</span><span class="sxs-lookup"><span data-stu-id="b2359-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="b2359-118">**name**</span><span class="sxs-lookup"><span data-stu-id="b2359-118">**name**</span></span>|<span data-ttu-id="b2359-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b2359-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="b2359-120">指定的值**名称**属性中[ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)标记。</span><span class="sxs-lookup"><span data-stu-id="b2359-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2359-121">子元素</span><span class="sxs-lookup"><span data-stu-id="b2359-121">Child Elements</span></span>  
 <span data-ttu-id="b2359-122">无。</span><span class="sxs-lookup"><span data-stu-id="b2359-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2359-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b2359-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b2359-124">元素</span><span class="sxs-lookup"><span data-stu-id="b2359-124">Element</span></span>|<span data-ttu-id="b2359-125">描述</span><span class="sxs-lookup"><span data-stu-id="b2359-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2359-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b2359-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="b2359-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="b2359-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="b2359-128">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="b2359-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="b2359-129">包含类的 ASN.1 对象标识符 (OID) 映射。</span><span class="sxs-lookup"><span data-stu-id="b2359-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2359-130">备注</span><span class="sxs-lookup"><span data-stu-id="b2359-130">Remarks</span></span>  
 <span data-ttu-id="b2359-131">ASN.1 对象标识符标识中某些加密格式的算法。</span><span class="sxs-lookup"><span data-stu-id="b2359-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="b2359-132">将对象标识符映射到你想要识别的算法的友好名称。</span><span class="sxs-lookup"><span data-stu-id="b2359-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2359-133">示例</span><span class="sxs-lookup"><span data-stu-id="b2359-133">Example</span></span>  
 <span data-ttu-id="b2359-134">下面的示例演示如何使用 **\<oidEntry >** 元素将 RIPEMD-160 哈希算法的对象标识符映射到该哈希算法的实现。</span><span class="sxs-lookup"><span data-stu-id="b2359-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2359-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2359-135">See also</span></span>

- [<span data-ttu-id="b2359-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b2359-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b2359-137">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="b2359-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="b2359-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b2359-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="b2359-139">配置加密类</span><span class="sxs-lookup"><span data-stu-id="b2359-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="b2359-140">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="b2359-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
