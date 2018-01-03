---
title: "指定入口点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7486820d78d767b8eb79397d6179ac81efc27968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="d5212-102">指定入口点</span><span class="sxs-lookup"><span data-stu-id="d5212-102">Specifying an Entry Point</span></span>
<span data-ttu-id="d5212-103">入口点标识 DLL 中的函数位置。</span><span class="sxs-lookup"><span data-stu-id="d5212-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="d5212-104">在托管项目中，目标函数的原始名称或序号入口点跨越互操作边界标识该函数。</span><span class="sxs-lookup"><span data-stu-id="d5212-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="d5212-105">此外，可将入口点映射到其他名称，有效地重命名该函数。</span><span class="sxs-lookup"><span data-stu-id="d5212-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="d5212-106">以下列表列出了重命名 DLL 函数的可能原因：</span><span class="sxs-lookup"><span data-stu-id="d5212-106">Following is a list of possible reasons to rename a DLL function:</span></span>  
  
-   <span data-ttu-id="d5212-107">避免使用区分大小写的 API 函数名</span><span class="sxs-lookup"><span data-stu-id="d5212-107">To avoid using case-sensitive API function names</span></span>  
  
-   <span data-ttu-id="d5212-108">符合现有的命名标准</span><span class="sxs-lookup"><span data-stu-id="d5212-108">To comply with existing naming standards</span></span>  
  
-   <span data-ttu-id="d5212-109">提供采用不同数据类型的函数（通过声明同一 DLL 函数的多个版本）</span><span class="sxs-lookup"><span data-stu-id="d5212-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
-   <span data-ttu-id="d5212-110">简化对包含 ANSI 和 Unicode 版本的 API 的使用</span><span class="sxs-lookup"><span data-stu-id="d5212-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="d5212-111">本主题说明如何在托管代码中重命名 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="d5212-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="d5212-112">重命名 Visual Basic 中的函数</span><span class="sxs-lookup"><span data-stu-id="d5212-112">Renaming a Function in Visual Basic</span></span>  
 <span data-ttu-id="d5212-113">Visual Basic 在 Declare 语句中使用 Function 关键字设置 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> 字段。</span><span class="sxs-lookup"><span data-stu-id="d5212-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="d5212-114">下面的示例演示了一个基本声明。</span><span class="sxs-lookup"><span data-stu-id="d5212-114">The following example shows a basic declaration.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 <span data-ttu-id="d5212-115">如下例所示，通过在定义中包括 Alias 关键字，可以用 MsgBox 替换 MessageBox 入口点。</span><span class="sxs-lookup"><span data-stu-id="d5212-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="d5212-116">在这两个示例中，Auto 关键字使你无需指定入口点的字符集版本。</span><span class="sxs-lookup"><span data-stu-id="d5212-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="d5212-117">有关选择字符集的详细信息，请参阅[指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)。</span><span class="sxs-lookup"><span data-stu-id="d5212-117">For more information about selecting a character set, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="d5212-118">重命名 C# 和 C++ 中的函数</span><span class="sxs-lookup"><span data-stu-id="d5212-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="d5212-119">可使用 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> 字段通过名称或序号指定 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="d5212-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="d5212-120">如果方法定义中函数的名称与 DLL 中入口点的名称相同，则不必使用 EntryPoint 字段显式地标识函数。</span><span class="sxs-lookup"><span data-stu-id="d5212-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="d5212-121">否则，使用以下属性形式之一指示名称或序号：</span><span class="sxs-lookup"><span data-stu-id="d5212-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 <span data-ttu-id="d5212-122">请注意，序号前必须带有井号 (#)。</span><span class="sxs-lookup"><span data-stu-id="d5212-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="d5212-123">下面的示例演示如何使用 EntryPoint 字段将代码中的 MessageBoxA 替换为 MsgBox。</span><span class="sxs-lookup"><span data-stu-id="d5212-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5212-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5212-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="d5212-125">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="d5212-125">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="d5212-126">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="d5212-126">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="d5212-127">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="d5212-127">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
