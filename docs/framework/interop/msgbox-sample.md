---
title: "MsgBox 示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f6ef3407c5f06e04d7a8b882a6458f236886dea
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="msgbox-sample"></a><span data-ttu-id="1a348-102">MsgBox 示例</span><span class="sxs-lookup"><span data-stu-id="1a348-102">MsgBox Sample</span></span>
<span data-ttu-id="1a348-103">此示例演示如何通过值将字符串类型作为 In 参数传递，以及何时使用 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>、<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 和 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> 字段。</span><span class="sxs-lookup"><span data-stu-id="1a348-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="1a348-104">MsgBox 示例使用以下未托管的函数（与其原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="1a348-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="1a348-105">从 User32.dll 导出的 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="1a348-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="1a348-106">在此示例中，`LibWrap` 类包含 `MsgBoxSample` 类调用的每一个未托管的函数的托管原型。</span><span class="sxs-lookup"><span data-stu-id="1a348-106">In this sample, the `LibWrap` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="1a348-107">托管原型方法 `MsgBox``MsgBox2` 和 `MsgBox3` 对于相同的未托管的函数有不同的声明。</span><span class="sxs-lookup"><span data-stu-id="1a348-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="1a348-108">由于指定为 ANSI 的字符类型与 Unicode 函数名称的入口点 `MessageBoxW` 不匹配，`MsgBox2` 的声明会在消息框中生成不正确的输出。</span><span class="sxs-lookup"><span data-stu-id="1a348-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="1a348-109">`MsgBox3` 的声明会在 EntryPoint、CharSet 和 ExactSpelling 字段之间创建不匹配。</span><span class="sxs-lookup"><span data-stu-id="1a348-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="1a348-110">调用时，`MsgBox3` 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="1a348-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="1a348-111">有关字符串命名和名称封送处理的详细信息，请参阅[指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)。</span><span class="sxs-lookup"><span data-stu-id="1a348-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="1a348-112">声明原型</span><span class="sxs-lookup"><span data-stu-id="1a348-112">Declaring Prototypes</span></span>  
 <span data-ttu-id="1a348-113">[!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)] [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)] [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="1a348-113">[!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)] [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)] [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]</span></span>  
  
## <a name="calling-functions"></a><span data-ttu-id="1a348-114">调用函数</span><span class="sxs-lookup"><span data-stu-id="1a348-114">Calling Functions</span></span>  
 <span data-ttu-id="1a348-115">[!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)] [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)] [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="1a348-115">[!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)] [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)] [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a348-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a348-116">See Also</span></span>  
 <span data-ttu-id="1a348-117">[封送处理字符串](../../../docs/framework/interop/marshaling-strings.md) </span><span class="sxs-lookup"><span data-stu-id="1a348-117">[Marshaling Strings](../../../docs/framework/interop/marshaling-strings.md) </span></span>  
 <span data-ttu-id="1a348-118">[平台调用数据类型](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span><span class="sxs-lookup"><span data-stu-id="1a348-118">[Platform Invoke Data Types](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span></span>  
 <span data-ttu-id="1a348-119">[字符串的默认封送处理](../../../docs/framework/interop/default-marshaling-for-strings.md) </span><span class="sxs-lookup"><span data-stu-id="1a348-119">[Default Marshaling for Strings](../../../docs/framework/interop/default-marshaling-for-strings.md) </span></span>  
 <span data-ttu-id="1a348-120">[在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md) </span><span class="sxs-lookup"><span data-stu-id="1a348-120">[Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md) </span></span>  
 [<span data-ttu-id="1a348-121">指定字符集</span><span class="sxs-lookup"><span data-stu-id="1a348-121">Specifying a Character Set</span></span>](../../../docs/framework/interop/specifying-a-character-set.md)

