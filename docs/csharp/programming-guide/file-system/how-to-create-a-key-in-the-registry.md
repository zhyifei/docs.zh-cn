---
title: 如何：在注册表中创建注册表项 (Visual C#)
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 0982baea2327daf23726ef269d53388d6011703d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596149"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="1f628-102">如何：在注册表中创建注册表项 (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="1f628-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="1f628-103">本示例将值对“Name”和“Isabella”添加到当前用户注册表中的项“Names”之下。</span><span class="sxs-lookup"><span data-stu-id="1f628-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f628-104">示例</span><span class="sxs-lookup"><span data-stu-id="1f628-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f628-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="1f628-105">Compiling the Code</span></span>  
  
- <span data-ttu-id="1f628-106">复制代码，并将其粘贴到控制台应用程序的 `Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="1f628-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="1f628-107">将 `Names` 参数替换为直接存在于注册表 HKEY_CURRENT_USER 节点下的项的名称。</span><span class="sxs-lookup"><span data-stu-id="1f628-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="1f628-108">将 `Name` 参数替换为直接存在于“Names”节点下的值的名称。</span><span class="sxs-lookup"><span data-stu-id="1f628-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1f628-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1f628-109">Robust Programming</span></span>  
 <span data-ttu-id="1f628-110">检查注册表结构，查找适合项的位置。</span><span class="sxs-lookup"><span data-stu-id="1f628-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="1f628-111">例如，可能需要打开当前用户的 Software 项，并用公司的名称创建一项。</span><span class="sxs-lookup"><span data-stu-id="1f628-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="1f628-112">然后将注册表值添加到公司的项上。</span><span class="sxs-lookup"><span data-stu-id="1f628-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="1f628-113">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="1f628-113">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="1f628-114">项的名称为空。</span><span class="sxs-lookup"><span data-stu-id="1f628-114">The name of the key is null.</span></span>  
  
- <span data-ttu-id="1f628-115">用户没有创建注册表项的权限。</span><span class="sxs-lookup"><span data-stu-id="1f628-115">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="1f628-116">项名称超过 255 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="1f628-116">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="1f628-117">项已关闭。</span><span class="sxs-lookup"><span data-stu-id="1f628-117">The key is closed.</span></span>  
  
- <span data-ttu-id="1f628-118">注册表项为只读。</span><span class="sxs-lookup"><span data-stu-id="1f628-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1f628-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="1f628-119">.NET Framework Security</span></span>  
 <span data-ttu-id="1f628-120">将数据写入用户文件夹 `Microsoft.Win32.Registry.CurrentUser` 比写入本地计算机 `Microsoft.Win32.Registry.LocalMachine` 更安全。</span><span class="sxs-lookup"><span data-stu-id="1f628-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="1f628-121">创建注册表值时，需要确定该值已存在时应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1f628-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="1f628-122">另一进程（可能是恶意进程）可能已创建了该值，并拥有对该值的访问权。</span><span class="sxs-lookup"><span data-stu-id="1f628-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="1f628-123">将数据放入注册表值后，其他进程即可使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="1f628-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="1f628-124">若要防止出现这种情况，请使用 `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="1f628-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="1f628-125">方法。</span><span class="sxs-lookup"><span data-stu-id="1f628-125">method.</span></span> <span data-ttu-id="1f628-126">如果项不存在，则该方法返回 null。</span><span class="sxs-lookup"><span data-stu-id="1f628-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="1f628-127">即使注册表项受访问控制列表 (ACL) 保护，在注册表中以纯文本形式存储机密信息（例如密码）也不安全。</span><span class="sxs-lookup"><span data-stu-id="1f628-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f628-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f628-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="1f628-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1f628-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1f628-130">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1f628-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
- <span data-ttu-id="1f628-131">[Read, write and delete from the registry with C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)（使用 C# 在注册表中执行读取、写入和删除操作）</span><span class="sxs-lookup"><span data-stu-id="1f628-131">[Read, write and delete from the registry with C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)</span></span>
