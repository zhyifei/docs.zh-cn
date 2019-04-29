---
title: Windows Identity Foundation 配置架构
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 9c8009b4d95e5aa2c3d9bb8a8958040127a9e628
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791664"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="4b5ca-102">Windows Identity Foundation 配置架构</span><span class="sxs-lookup"><span data-stu-id="4b5ca-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="4b5ca-103">本节中的主题介绍了 Windows Identity Foundation (WIF) 配置架构。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="4b5ca-104">此外可以配置为通过由框架公开的类使用 WIF 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="4b5ca-105">在处理架构中相关元素的几节中提到了这些类。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="4b5ca-106">以下显示由 WIF 配置架构公开的基本 XML 标记结构。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="4b5ca-107">系统会省略属性。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-107">Attributes are omitted.</span></span> <span data-ttu-id="4b5ca-108">突出显示的注释描述架构的主要组件。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<system.identityModel>  
    <!-- Service Configuration -->  
    <identityConfiguration>  
        <caches>  
            <sessionSecurityTokenCache />  
            <tokenReplayCache />  
        </caches>  
  
        <certificateValidation>  
            <certificateValidator />   
        </certificateValidation>  
  
        <claimsAuthenticationManager />  
  
        <claimsAuthorizationManager>  
            <optionalConfigurationElement>  
        </claimsAuthorizationManager>  
  
        <claimTypeRequired>  
            <claimType />   
        </claimTypeRequired>  
  
        <tokenReplayDetection />  
  
        <!-- Security Token Handler Collection Configuration -->  
        <securityTokenHandlers>  
            <add>  
                <!-- Can take an optional configuration element which can be one of  
                     the following or a custom element -->  
                <samlSecurityTokenHandlerRequirement>  
                    <nameClaimType>  
                    <roleClaimType>   
                </samlSecurityTokenHandlerRequirement>  
  
                <sessionSecurityTokenHandlerRequirement />  
                <x509SecurityTokenHandlerRequirement />  
                <userNameSecurityTokenHandlerRequirement />  
            </add>  
            <clear />  
            <remove />  
            <securityTokenHandlerConfiguration>  
                <audienceUris>  
                    <add>  
                    <clear>  
                    <remove>  
                </audienceUris>  
  
                <caches>  
                    <sessionSecurityTokenCache />  
                    <tokenReplayCache />  
                </caches>  
  
                <certificateValidation>  
                    <certificateValidator>   
                </certificateValidation>  
  
                <issuerNameRegistry>  
                    <!-- Can take an optional configuration element which can be   
                         the <trustedIssuers> element to configure a configuration-based  
                         issuer name registry or can be a custom element -->  
                    <trustedIssuers>  
                        <add>  
                        <clear>  
                        <remove>  
                    </trustedIssuers>  
                </issuerNameRegistry>  
  
                <issuerTokenResolver />  
                <serviceTokenResolver />  
                <tokenReplayDetection />  
            </securityTokenHandlerConfiguration>  
        </securityTokenHandlers>  
    </identityConfiguration>  
</system.identityModel>  
  
<system.identityModel.services>  
    <!-- Federation Authentication Configuration -->  
    <federatedAuthentication>  
        <cookieHandler>  
            <chunkedCookieHandler />  
            <customCookieHandler />  
        </cookieHandler>  
  
        <serviceCertificate>  
            <certificateReference>  
        </serviceCertificate>  
  
        <wsFederation />  
    </federatedAuthentication>  
</system.identityModel.services>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="4b5ca-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="4b5ca-109">In This Section</span></span>  
 <span data-ttu-id="4b5ca-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 提供用于在应用程序中启用 WIF 选项的配置。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="4b5ca-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 提供使用 WIF 的被动联合的配置。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="4b5ca-112">配置会话身份验证模块 (SAM) 和联合身份验证模块 (WSFAM)。</span><span class="sxs-lookup"><span data-stu-id="4b5ca-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
