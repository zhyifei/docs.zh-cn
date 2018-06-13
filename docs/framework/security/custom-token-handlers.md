---
title: 自定义令牌处理程序
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 18be4babf7e9cfbfe9ebfb43da6f98a8544b2fe6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399972"
---
# <a name="custom-token-handlers"></a><span data-ttu-id="2e01b-102">自定义令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="2e01b-102">Custom Token Handlers</span></span>
<span data-ttu-id="2e01b-103">本主题讨论 WIF 中的令牌处理程序，以及如何使用它们处理令牌。</span><span class="sxs-lookup"><span data-stu-id="2e01b-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="2e01b-104">还介绍为 WIF 中默认不支持的令牌类型创建自定义令牌处理程序所需的内容。</span><span class="sxs-lookup"><span data-stu-id="2e01b-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="2e01b-105">WIF 中的令牌处理程序简介</span><span class="sxs-lookup"><span data-stu-id="2e01b-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="2e01b-106">WIF 依赖安全令牌处理程序为信赖方 (RP) 应用程序或安全令牌服务 (STS) 创建、读取、写入和验证令牌。</span><span class="sxs-lookup"><span data-stu-id="2e01b-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="2e01b-107">令牌处理程序是扩展点，用于在 WIF 管道中添加自定义令牌处理程序，或自定义现有令牌处理程序管理令牌的方式。</span><span class="sxs-lookup"><span data-stu-id="2e01b-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="2e01b-108">为了根据需要更改功能，WIF 提供九个可以修改或完全替代的内置安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e01b-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="2e01b-109">WIF 中的内置安全令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="2e01b-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="2e01b-110">WIF 4.5 包括九个从抽象基类 <xref:System.IdentityModel.Tokens.SecurityTokenHandler> 派生的安全令牌处理程序类：</span><span class="sxs-lookup"><span data-stu-id="2e01b-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="2e01b-111">添加自定义令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="2e01b-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="2e01b-112">一些令牌类型（例如，简单 Web 令牌 (SWT) 和 JSON Web 令牌 (JWT)）没有 WIF 提供的内置令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e01b-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="2e01b-113">对于这些令牌类型以及其他没有内置处理程序的令牌类型，必须执行以下步骤来创建自定义令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e01b-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="2e01b-114">添加自定义令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="2e01b-114">Adding a custom token handler</span></span>  
  
1.  <span data-ttu-id="2e01b-115">创建一个从 <xref:System.IdentityModel.Tokens.SecurityTokenHandler> 派生的新类。</span><span class="sxs-lookup"><span data-stu-id="2e01b-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2.  <span data-ttu-id="2e01b-116">重写以下方法，提供自己的实现：</span><span class="sxs-lookup"><span data-stu-id="2e01b-116">Override the following methods and provide your own implementation:</span></span>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  <span data-ttu-id="2e01b-117">在应用于 WIF 的 \<system.identityModel> 部分内的 Web.config 或 App.config 文件中，添加对新自定义令牌处理程序的引用。</span><span class="sxs-lookup"><span data-stu-id="2e01b-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="2e01b-118">例如，以下配置标记指定了位于 CustomToken 命名空间中名为 MyCustomTokenHandler 的新令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e01b-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="2e01b-119">请注意，如果提供自己的令牌处理程序来处理已有内置令牌处理程序的令牌类型，必须添加 \<remove> 元素，才能删除默认处理程序和改用自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e01b-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="2e01b-120">例如，以下配置将使用自定义令牌处理程序替换默认 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>：</span><span class="sxs-lookup"><span data-stu-id="2e01b-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789">  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
