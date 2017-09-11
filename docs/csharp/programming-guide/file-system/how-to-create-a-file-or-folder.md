---
title: "如何：创建文件或文件夹（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 150190eeef829bd0431eeea7789025b9905553e3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="eab89-102">如何：创建文件或文件夹（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="eab89-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="eab89-103">可通过编程方式在计算机上创建文件夹、子文件夹和子文件夹中的文件，并将数据写入文件。</span><span class="sxs-lookup"><span data-stu-id="eab89-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eab89-104">示例</span><span class="sxs-lookup"><span data-stu-id="eab89-104">Example</span></span>  
 <span data-ttu-id="eab89-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eab89-105">[!code-cs[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]</span></span>  
  
 <span data-ttu-id="eab89-106">如果文件夹已存在，<xref:System.IO.Directory.CreateDirectory%2A> 不执行任何操作，未引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="eab89-106">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="eab89-107">但 <xref:System.IO.File.Create%2A?displayProperty=fullName> 用新文件替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="eab89-107">However, <xref:System.IO.File.Create%2A?displayProperty=fullName> replaces an existing file with a new file.</span></span> <span data-ttu-id="eab89-108">本示例使用 `if`-`else` 语句阻止替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="eab89-108">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="eab89-109">通过在示例中作出以下更改，可根据具有特定名称的文件是否存在来指定不同的结果。</span><span class="sxs-lookup"><span data-stu-id="eab89-109">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="eab89-110">如果该文件不存在，代码就会创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="eab89-110">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="eab89-111">如果该文件存在，代码就会将数据追加到该文件中。</span><span class="sxs-lookup"><span data-stu-id="eab89-111">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="eab89-112">指定一个非随机文件名。</span><span class="sxs-lookup"><span data-stu-id="eab89-112">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="eab89-113">用以下代码中的 `using` 语句替换 `if`-`else` 语句。</span><span class="sxs-lookup"><span data-stu-id="eab89-113">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="eab89-114">多次运行此示例，验证数据是否每次都添加到了文件中。</span><span class="sxs-lookup"><span data-stu-id="eab89-114">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="eab89-115">有关可尝试的 `FileMode` 值，请参阅 <xref:System.IO.FileMode>。</span><span class="sxs-lookup"><span data-stu-id="eab89-115">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="eab89-116">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="eab89-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="eab89-117">文件夹名称格式不正确。</span><span class="sxs-lookup"><span data-stu-id="eab89-117">The folder name is malformed.</span></span> <span data-ttu-id="eab89-118">例如，它包含非法字符或它仅为空格（<xref:System.ArgumentException> 类）。</span><span class="sxs-lookup"><span data-stu-id="eab89-118">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="eab89-119">使用 <xref:System.IO.Path> 类创建有效的路径名。</span><span class="sxs-lookup"><span data-stu-id="eab89-119">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="eab89-120">要创建的文件夹的父文件夹为只读（<xref:System.IO.IOException> 类）。</span><span class="sxs-lookup"><span data-stu-id="eab89-120">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="eab89-121">文件夹名为 `null`<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="eab89-121">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="eab89-122">文件夹名过长（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="eab89-122">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="eab89-123">文件夹仅为冒号“:”（<xref:System.IO.PathTooLongException> 类）。</span><span class="sxs-lookup"><span data-stu-id="eab89-123">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="eab89-124">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="eab89-124">.NET Framework Security</span></span>  
 <span data-ttu-id="eab89-125">可能在部分信任场景中引发 <xref:System.Security.SecurityException> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="eab89-125">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="eab89-126">如果没有创建文件夹的权限，则本示例引发 <xref:System.UnauthorizedAccessException> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="eab89-126">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab89-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eab89-127">See Also</span></span>  
 <span data-ttu-id="eab89-128"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="eab89-128"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="eab89-129">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eab89-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="eab89-130">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="eab89-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

