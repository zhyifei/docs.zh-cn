---
title: 平台调用 (P/Invoke)
description: 了解如何在 .NET 中通过 P/Invoke 调用本机函数。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: f243fee2b246afff36732d469c6295d7e4b2fd87
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411363"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="6fe36-103">平台调用 (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="6fe36-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="6fe36-104">P/Invoke 是可用于从托管代码访问非托管库中的结构、回调和函数的一种技术。</span><span class="sxs-lookup"><span data-stu-id="6fe36-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="6fe36-105">大多数 P/Invoke API 包含在以下两个命名空间中：`System` 和 `System.Runtime.InteropServices`。</span><span class="sxs-lookup"><span data-stu-id="6fe36-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="6fe36-106">使用这两个命名空间可提供用于描述如何与本机组件通信的工具。</span><span class="sxs-lookup"><span data-stu-id="6fe36-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="6fe36-107">我们从最常见的示例着手。该示例在托管代码中调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="6fe36-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="6fe36-108">让我们从命令行应用程序显示一个消息框：</span><span class="sxs-lookup"><span data-stu-id="6fe36-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="6fe36-109">上述示例非常简单，但确实演示了从托管代码调用非托管函数所需执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6fe36-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="6fe36-110">让我们逐步分析该示例：</span><span class="sxs-lookup"><span data-stu-id="6fe36-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="6fe36-111">第 1 行显示 `System.Runtime.InteropServices` 命名空间（用于保存全部所需项）的 using 语句。</span><span class="sxs-lookup"><span data-stu-id="6fe36-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="6fe36-112">第 7 行引入 `DllImport` 属性。</span><span class="sxs-lookup"><span data-stu-id="6fe36-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="6fe36-113">此特性至关重要，因为它告诉运行时要加载非托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="6fe36-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="6fe36-114">传入的字符串是目标函数所在的 DLL。</span><span class="sxs-lookup"><span data-stu-id="6fe36-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="6fe36-115">第 8 行显示了 P/Invoke 的关键作用。</span><span class="sxs-lookup"><span data-stu-id="6fe36-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="6fe36-116">它定义了一个托管方法，该方法的签名与非托管方法**完全相同**。</span><span class="sxs-lookup"><span data-stu-id="6fe36-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="6fe36-117">可以看到，声明中包含一个新关键字 `extern`，告诉运行时这是一个外部方法。调用该方法时，运行时应在 `DllImport` 特性中指定的 DLL 内查找该方法。</span><span class="sxs-lookup"><span data-stu-id="6fe36-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="6fe36-118">该示例的剩余部分无非就是调用该方法，就像调用其他任何托管方法一样。</span><span class="sxs-lookup"><span data-stu-id="6fe36-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="6fe36-119">在 macOS 上也可以使用类似的示例。</span><span class="sxs-lookup"><span data-stu-id="6fe36-119">The sample is similar for macOS.</span></span> <span data-ttu-id="6fe36-120">需要更改 `DllImport` 属性中的库名称，因为 macOS 使用不同的方案来命名动态库。</span><span class="sxs-lookup"><span data-stu-id="6fe36-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="6fe36-121">下面的示例使用 `getpid(2)` 函数获取应用程序的进程 ID，然后控制台上列显该 ID：</span><span class="sxs-lookup"><span data-stu-id="6fe36-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="6fe36-122">它在 Linux 上也是类似的。</span><span class="sxs-lookup"><span data-stu-id="6fe36-122">It is also similar on Linux.</span></span> <span data-ttu-id="6fe36-123">函数名称相同，因为 `getpid(2)` 是标准 [POSIX](https://en.wikipedia.org/wiki/POSIX) 系统调用。</span><span class="sxs-lookup"><span data-stu-id="6fe36-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="6fe36-124">从非托管代码调用托管代码</span><span class="sxs-lookup"><span data-stu-id="6fe36-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="6fe36-125">运行时允许通信流量双向流通，这样，便可以使用函数指针从本机函数回调托管代码。</span><span class="sxs-lookup"><span data-stu-id="6fe36-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="6fe36-126">在托管代码中，与函数指针最接近的功能就是**委托**，正是凭借这个功能，才能从本机代码回调托管代码。</span><span class="sxs-lookup"><span data-stu-id="6fe36-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="6fe36-127">此功能的使用方式类似于上面所述的从托管代码调用本机进程。</span><span class="sxs-lookup"><span data-stu-id="6fe36-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="6fe36-128">对于给定的回调，需要定义一个与签名匹配的委托，并将其传入外部方法。</span><span class="sxs-lookup"><span data-stu-id="6fe36-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="6fe36-129">运行时将负责处理所有剩余工作。</span><span class="sxs-lookup"><span data-stu-id="6fe36-129">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="6fe36-130">在演练示例之前，最好是回顾一下所要使用的非托管函数的签名。</span><span class="sxs-lookup"><span data-stu-id="6fe36-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="6fe36-131">要调用以枚举所有窗口的函数具有以下签名：`BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="6fe36-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="6fe36-132">第一个参数是回调。</span><span class="sxs-lookup"><span data-stu-id="6fe36-132">The first parameter is a callback.</span></span> <span data-ttu-id="6fe36-133">该回调具有以下签名：`BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="6fe36-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="6fe36-134">现在，让我们来演练示例：</span><span class="sxs-lookup"><span data-stu-id="6fe36-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="6fe36-135">示例中的第 9 行定义与非托管代码中回调签名匹配的委托。</span><span class="sxs-lookup"><span data-stu-id="6fe36-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="6fe36-136">请注意如何在托管代码中使用 `IntPtr` 表示 LPARAM 和 HWND 类型。</span><span class="sxs-lookup"><span data-stu-id="6fe36-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="6fe36-137">第 13 和 14 行从 user32.dll 库中引入 `EnumWindows` 函数。</span><span class="sxs-lookup"><span data-stu-id="6fe36-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="6fe36-138">第 17 - 20 行实现该委托。</span><span class="sxs-lookup"><span data-stu-id="6fe36-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="6fe36-139">在这个简单的示例中，我们只要将句柄输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="6fe36-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="6fe36-140">最后，第 24 行调用外部方法并传入委托。</span><span class="sxs-lookup"><span data-stu-id="6fe36-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="6fe36-141">下面显示了 Linux 和 macOS 示例。</span><span class="sxs-lookup"><span data-stu-id="6fe36-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="6fe36-142">在这些平台上，我们可以使用 C 库 `libc` 中的 `ftw` 函数。</span><span class="sxs-lookup"><span data-stu-id="6fe36-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="6fe36-143">此函数用于遍历目录层次结构，它使用指向某个函数的指针作为其参数之一。</span><span class="sxs-lookup"><span data-stu-id="6fe36-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="6fe36-144">该函数具有以下签名：`int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`。</span><span class="sxs-lookup"><span data-stu-id="6fe36-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="6fe36-145">macOS 示例使用相同的函数，唯一的差别在于 `DllImport` 特性的自变量，因为 macOS 将 `libc` 保留在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="6fe36-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="6fe36-146">上面两个示例都依赖于参数，在这两种情况下，参数是作为托管类型提供的。</span><span class="sxs-lookup"><span data-stu-id="6fe36-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="6fe36-147">运行时将采取“适当的措施”，在另一个平台上将这些代码处理成等效的代码。</span><span class="sxs-lookup"><span data-stu-id="6fe36-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="6fe36-148">[类型封送](type-marshalling.md)页介绍了如何将类型封送到本机代码。</span><span class="sxs-lookup"><span data-stu-id="6fe36-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="6fe36-149">更多资源</span><span class="sxs-lookup"><span data-stu-id="6fe36-149">More resources</span></span>

*   <span data-ttu-id="6fe36-150">[PInvoke.net wiki](https://www.pinvoke.net/) 是一个极佳的 Wiki 站点，其中提供了有关常用 Win32 API 以及如何调用这些 API 的信息。</span><span class="sxs-lookup"><span data-stu-id="6fe36-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="6fe36-151">MSDN 上的 P/Invoke</span><span class="sxs-lookup"><span data-stu-id="6fe36-151">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="6fe36-152">有关 P/Invoke 的 Mono 文档</span><span class="sxs-lookup"><span data-stu-id="6fe36-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
