---
title: 如何：将用户信息分配给组连接
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
ms.openlocfilehash: 6d0be3ccfc0a0b4b032283b7ed34908f79774bb6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50049537"
---
# <a name="how-to-assign-user-information-to-group-connections"></a><span data-ttu-id="a4269-102">如何：将用户信息分配给组连接</span><span class="sxs-lookup"><span data-stu-id="a4269-102">How to: Assign User Information to Group Connections</span></span>

  
 <span data-ttu-id="a4269-103">以下示例演示如何将用户信息分配给组连接，其假定应用程序在调用此部分的代码之前设置了变量“UserName”、“SecurelyStoredPassword”和“域”，且“UserName”唯一。</span><span class="sxs-lookup"><span data-stu-id="a4269-103">The following example demonstrates how to assign user information to group connections, assuming that the application sets the variables *UserName*, *SecurelyStoredPassword*, and *Domain* before this section of code is called and that *UserName* is unique.</span></span>  
  
### <a name="to-assign-user-information-to-a-group-connection"></a><span data-ttu-id="a4269-104">将用户信息分配给组连接</span><span class="sxs-lookup"><span data-stu-id="a4269-104">To assign user information to a group connection</span></span>  
  
1.  <span data-ttu-id="a4269-105">创建连接组名称。</span><span class="sxs-lookup"><span data-stu-id="a4269-105">Create a connection group name.</span></span>  
  
    ```csharp  
    SHA1Managed Sha1 = new SHA1Managed();  
    Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
    String secureGroupName = Encoding.Default.GetString(updHash);  
    ```  
  
    ```vb  
    Dim Sha1 As New SHA1Managed()  
    Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
    Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
    ```  
  
2.  <span data-ttu-id="a4269-106">为特定的 URL 创建请求。</span><span class="sxs-lookup"><span data-stu-id="a4269-106">Create a request for a specific URL.</span></span> <span data-ttu-id="a4269-107">例如，以下代码为 URL `http://www.contoso.com.` 创建请求</span><span class="sxs-lookup"><span data-stu-id="a4269-107">For example, the following code creates a request for the URL `http://www.contoso.com.`</span></span>  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3.  <span data-ttu-id="a4269-108">为 Web 请求设置凭据和连接组名称，并调用 GetResponse 以检索 WebResponse 对象。</span><span class="sxs-lookup"><span data-stu-id="a4269-108">Set the credentials and Connection GroupName for the Web request, and call **GetResponse** to retrieve a **WebResponse** object.</span></span>  
  
    ```csharp  
    myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
    myWebRequest.ConnectionGroupName = secureGroupName;  
  
    WebResponse myWebResponse=myWebRequest.GetResponse();  
    ```  
  
    ```vb  
    myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
    myWebRequest.ConnectionGroupName = secureGroupName  
  
    Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
    ```  
  
4.  <span data-ttu-id="a4269-109">使用 WebRespose 对象后关闭响应流。</span><span class="sxs-lookup"><span data-stu-id="a4269-109">Close the response stream after using the WebRespose object.</span></span>  
  
    ```csharp  
    MyWebResponse.Close();  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 <span data-ttu-id="a4269-110">示例</span><span class="sxs-lookup"><span data-stu-id="a4269-110">Example</span></span>  
  
```csharp  
// Create a connection group name.  
SHA1Managed Sha1 = new SHA1Managed();  
Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
String secureGroupName = Encoding.Default.GetString(updHash);  
  
// Create a request for a specific URL.  
WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
  
myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
myWebRequest.ConnectionGroupName = secureGroupName;  
  
WebResponse myWebResponse=myWebRequest.GetResponse();  
  
// Insert the code that uses myWebResponse.  
  
MyWebResponse.Close();  
```  
  
```vb  
' Create a secure group name.  
Dim Sha1 As New SHA1Managed()  
Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
  
' Create a request for a specific URL.  
Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
  
myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
myWebRequest.ConnectionGroupName = secureGroupName  
  
Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
' Insert the code that uses myWebResponse.  
MyWebResponse.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4269-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4269-111">See Also</span></span>  
 [<span data-ttu-id="a4269-112">管理连接</span><span class="sxs-lookup"><span data-stu-id="a4269-112">Managing Connections</span></span>](../../../docs/framework/network-programming/managing-connections.md)  
 [<span data-ttu-id="a4269-113">连接分组</span><span class="sxs-lookup"><span data-stu-id="a4269-113">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)
