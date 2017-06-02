---
title: "自定义令牌处理程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 自定义令牌处理程序
本主题讨论在WIF标记处理程序，以及如何使用这些处理标记。  主题还包括什么是需要创建默认情况下在WIF不支持的标记类型的自定义标记处理程序。  
  
## 标记处理程序介绍WIF的  
 WIF依赖于安全标记处理程序创建，读取，编写，并验证该依赖方\(RP\)应用程序或安全标记服务的\(STS\)标记。  标记处理程序是扩展性点以便可以添加WIF管线的自定义标记处理程序，或自定义现有标记处理程序管理标记的方法。  WIF提供可修改或完全重写根据需要更改函数的九内置安全标记处理程序。  
  
## 内置WIF的安全标记处理程序  
 WIF 4.5包含从抽象基类 <xref:System.IdentityModel.Tokens.SecurityTokenHandler>派生的九安全标记处理程序选件类:  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## 添加自定义标记处理程序  
 这些标记类型，如简单的Web标记\(SWT\)和JSON Web标记\(JWT\)没有WIF提供的内置标记处理程序。  对于这些标记类型并且没有内置处理程序的其他的，需要执行以下步骤以创建自定义标记处理程序。  
  
#### 添加自定义标记处理程序  
  
1.  创建从 <xref:System.IdentityModel.Tokens.SecurityTokenHandler>派生的新选件类。  
  
2.  重写以下方法并提供自己的实现:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  添加对 *Web.config或* App.configfile的新自定义标记处理程序 *，* 在应用于WIF的 **\<system.identityModel\>** 节中。  例如，以下配置标记指定的位置 **CustomToken** 命名空间的新标记名为的处理程序 **MyCustomTokenHandler**。  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     请注意，如果提供您的标记处理程序处理已具有固定标记处理程序中的一个标记类型，需要添加 **\<remove\>** 元素删除默认处理程序和使用自定义处理程序。  例如，以下配置具有自定义标记处理程序替换默认 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> :  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type=”System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789”>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```