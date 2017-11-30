---
title: "WIF 配置架构约定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ad367a14373487698cd13c710998f1a5e6ccb7cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="wif-configuration-schema-conventions"></a><span data-ttu-id="3830f-102">WIF 配置架构约定</span><span class="sxs-lookup"><span data-stu-id="3830f-102">WIF Configuration Schema Conventions</span></span>
<span data-ttu-id="3830f-103">本主题讨论 Windows Identity Foundation (WIF) 配置主题中使用的约定并描述 [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 和 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 部分中使用的一些常见功能和属性。</span><span class="sxs-lookup"><span data-stu-id="3830f-103">This topic discusses conventions used throughout the Windows Identity Foundation (WIF) configuration topics and describes some common features and attributes used in the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) sections.</span></span>  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a><span data-ttu-id="3830f-104">模式</span><span class="sxs-lookup"><span data-stu-id="3830f-104">Modes</span></span>  
 <span data-ttu-id="3830f-105">许多 WIF 配置元素都具有 `mode` 属性。</span><span class="sxs-lookup"><span data-stu-id="3830f-105">Many of the WIF configuration elements have a `mode` attribute.</span></span> <span data-ttu-id="3830f-106">这一属性通常控制使用哪个类执行进程的特定部分，以及允许哪些配置元素作为当前元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="3830f-106">This attribute typically controls which class is used to do a particular part of the processing and which configuration elements are allowed as child elements of the current element.</span></span> <span data-ttu-id="3830f-107">如果配置文件中的元素因模式设置被忽略，会引发配置错误。</span><span class="sxs-lookup"><span data-stu-id="3830f-107">A configuration error will be raised if elements that are included in the configuration file are ignored because of the mode settings.</span></span>  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a><span data-ttu-id="3830f-108">Timespan 值</span><span class="sxs-lookup"><span data-stu-id="3830f-108">Timespan Values</span></span>  
 <span data-ttu-id="3830f-109">其中 <xref:System.TimeSpan> 用作属性的类型，请参阅 <xref:System.TimeSpan.Parse%28System.String%29> 方法以查看允许的格式。</span><span class="sxs-lookup"><span data-stu-id="3830f-109">Where <xref:System.TimeSpan> is used as the type of an attribute, see the <xref:System.TimeSpan.Parse%28System.String%29> method to see the allowed format.</span></span> <span data-ttu-id="3830f-110">此格式符合以下规范。</span><span class="sxs-lookup"><span data-stu-id="3830f-110">This format conforms to the following specification.</span></span>  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 <span data-ttu-id="3830f-111">例如，“30”、“30.00:00”、“30.00:00:00”都表示 30 天，并且“00:05”、“00:05:00”、“0.00:05:00.00”都表示 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="3830f-111">For example, "30", "30.00:00", "30.00:00:00" all mean 30 days; and "00:05", "00:05:00", "0.00:05:00.00" all mean 5 minutes.</span></span>  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a><span data-ttu-id="3830f-112">证书引用</span><span class="sxs-lookup"><span data-stu-id="3830f-112">Certificate References</span></span>  
 <span data-ttu-id="3830f-113">多个元素使用 `<certificateReference>` 元素获取对证书的引用。</span><span class="sxs-lookup"><span data-stu-id="3830f-113">Several elements take references to certificates using the `<certificateReference>` element.</span></span> <span data-ttu-id="3830f-114">引用证书时，可使用以下属性。</span><span class="sxs-lookup"><span data-stu-id="3830f-114">When referencing a certificate, the following attributes are available.</span></span>  
  
|||  
|-|-|  
|`storeLocation`|<span data-ttu-id="3830f-115"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> 枚举的一个值：`CurrentUser` 或 `CurrentMachine`。</span><span class="sxs-lookup"><span data-stu-id="3830f-115">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreLocation> enumeration: `CurrentUser` or `CurrentMachine`.</span></span>|  
|`storeName`|<span data-ttu-id="3830f-116"><xref:System.Security.Cryptography.X509Certificates.StoreName> 枚举的一个值；对此上下文最有用的是 `My` 和 `TrustedPeople`。</span><span class="sxs-lookup"><span data-stu-id="3830f-116">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreName> enumeration; the most useful for this context are `My` and `TrustedPeople`.</span></span>|  
|`x509FindType`|<span data-ttu-id="3830f-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 枚举的一个值；对此上下文最有用的是 `FindBySubjectName` 和 `FindByThumbprint`。</span><span class="sxs-lookup"><span data-stu-id="3830f-117">A value of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> enumeration; the most useful for this context are `FindBySubjectName` and `FindByThumbprint`.</span></span> <span data-ttu-id="3830f-118">若要消除错误的可能性，建议在生产环境中使用 `FindByThumbprint` 类型。</span><span class="sxs-lookup"><span data-stu-id="3830f-118">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span>|  
|`findValue`|<span data-ttu-id="3830f-119">用于查找证书的值，基于 `x509FindType` 属性。</span><span class="sxs-lookup"><span data-stu-id="3830f-119">The value used to find the certificate, based on the `x509FindType` attribute.</span></span> <span data-ttu-id="3830f-120">若要消除错误的可能性，建议在生产环境中使用 `FindByThumbprint` 类型。</span><span class="sxs-lookup"><span data-stu-id="3830f-120">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span> <span data-ttu-id="3830f-121">指定 `FindByThumbPrint` 时，此属性提取一个值，此值是证书指纹的十六进制字符串形式，如：“97249e1a5fa6bee5e515b82111ef524a4c91583f”。</span><span class="sxs-lookup"><span data-stu-id="3830f-121">When `FindByThumbPrint` is specified, this attribute takes a value that is the hexadecimal-string form of the certificate thumbprint; for example, "97249e1a5fa6bee5e515b82111ef524a4c91583f".</span></span>|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a><span data-ttu-id="3830f-122">自定义类型引用</span><span class="sxs-lookup"><span data-stu-id="3830f-122">Custom Type References</span></span>  
 <span data-ttu-id="3830f-123">多个元素使用 `type` 属性引用自定义类型。</span><span class="sxs-lookup"><span data-stu-id="3830f-123">Several elements reference custom types using the `type` attribute.</span></span> <span data-ttu-id="3830f-124">此属性应指定自定义类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3830f-124">This attribute should specify the name of the custom type.</span></span> <span data-ttu-id="3830f-125">若要从全局程序集缓存 (GAC) 中引用类型，应使用强名称。</span><span class="sxs-lookup"><span data-stu-id="3830f-125">To reference a type from the Global Assembly Cache (GAC), a strong name should be used.</span></span> <span data-ttu-id="3830f-126">若要从 Bin/ 目录中引用类型，可使用简单的程序集限定的引用。</span><span class="sxs-lookup"><span data-stu-id="3830f-126">To reference a type from an assembly in the Bin/ directory, a simple assembly-qualified reference may be used.</span></span> <span data-ttu-id="3830f-127">App_Code/ 目录中定义的类型也可以在没有限定程序集时仅通过指定类型名称引用。</span><span class="sxs-lookup"><span data-stu-id="3830f-127">Types defined in the App_Code/ directory may also be referenced by simply specifying the type name with no qualifying assembly.</span></span>  
  
 <span data-ttu-id="3830f-128">自定义类型应从指定类型中派生，同时应提供 `public` 默认（0 参数）构造函数。</span><span class="sxs-lookup"><span data-stu-id="3830f-128">Custom types must be derived from the type specified and they must provide a `public` default (0 argument) constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3830f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3830f-129">See Also</span></span>  
 [<span data-ttu-id="3830f-130">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3830f-130">\<system.identityModel></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [<span data-ttu-id="3830f-131">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="3830f-131">\<system.identityModel.services></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
