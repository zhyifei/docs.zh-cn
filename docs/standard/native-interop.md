---
title: 本机互操作性
description: 了解如何与 .NET 中的本机组件交互。
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.openlocfilehash: 7da86cfe483a2355c53206f4c491fbd07e4c3046
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="native-interoperability"></a><span data-ttu-id="66e23-103">本机互操作性</span><span class="sxs-lookup"><span data-stu-id="66e23-103">Native Interoperability</span></span>

<span data-ttu-id="66e23-104">在本文档中，我们将略为深入地探讨使用 .NET 可实现“本机互操作性”的所有三种方式。</span><span class="sxs-lookup"><span data-stu-id="66e23-104">In this document, we will dive a little bit deeper into all three ways of doing "native interoperability" that are available using .NET.</span></span>

<span data-ttu-id="66e23-105">调用本机代码的原因有以下几种：</span><span class="sxs-lookup"><span data-stu-id="66e23-105">There are a few of reasons why you would want to call into native code:</span></span>

*   <span data-ttu-id="66e23-106">在操作系统附带的 API 有很多并不在托管类库中。</span><span class="sxs-lookup"><span data-stu-id="66e23-106">Operating Systems come with a large volume of APIs that are not present in the managed class libraries.</span></span> <span data-ttu-id="66e23-107">最好的例子就是对硬件或操作系统管理功能的访问。</span><span class="sxs-lookup"><span data-stu-id="66e23-107">A prime example for this would be access to hardware or operating system management functions.</span></span>
*   <span data-ttu-id="66e23-108">与包含或者可以生成 C 式 ABI（本机 ABI）的其他组件通信。</span><span class="sxs-lookup"><span data-stu-id="66e23-108">Communicating with other components that have or can produce C-style ABIs (native ABIs).</span></span> <span data-ttu-id="66e23-109">例如，这包括通过 [Java 本机接口 (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) 或其他任何可以生成本机组件的托管语言公开的 Java 代码。</span><span class="sxs-lookup"><span data-stu-id="66e23-109">This covers, for example, Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
*   <span data-ttu-id="66e23-110">在 Windows 上，安装的大部分软件（例如 Microsoft Office 套件）会注册 COM 组件，用于代表软件的程序，并使开发人员能够自动化或者使用它们。</span><span class="sxs-lookup"><span data-stu-id="66e23-110">On Windows, most of the software that gets installed, such as Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="66e23-111">在这种情况下，也需要本机互操作性。</span><span class="sxs-lookup"><span data-stu-id="66e23-111">This also requires native interoperability.</span></span>

<span data-ttu-id="66e23-112">当然，上述列表并未包括开发人员想要/偏向于/需要与本机组件交互的所有可能场合与情境。</span><span class="sxs-lookup"><span data-stu-id="66e23-112">Of course, the list above does not cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="66e23-113">例如，.NET 类库使用本机互操作性支持来实现其相当多的 API，如控制台支持和操作、文件系统访问，等等。</span><span class="sxs-lookup"><span data-stu-id="66e23-113">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="66e23-114">但务必知道，本机互操作性总能提供相应的选项来满足用户的需要。</span><span class="sxs-lookup"><span data-stu-id="66e23-114">However, it is important to note that there is an option, should one need it.</span></span>

> [!NOTE]
> <span data-ttu-id="66e23-115">本文档中的大部分示例是针对 .NET Core 支持的所有三个平台（Windows、Linux 和 macOS）提供的。</span><span class="sxs-lookup"><span data-stu-id="66e23-115">Most of the examples in this document will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="66e23-116">但是，在某些简短的演示性示例中，只显示了一个使用 Windows 文件名和扩展名（即，库的扩展名“dll”）的例子。</span><span class="sxs-lookup"><span data-stu-id="66e23-116">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="66e23-117">这并不意味着这些功能不能在 Linux 或 macOS 上使用，只是出于方便而未提到这些平台。</span><span class="sxs-lookup"><span data-stu-id="66e23-117">This does not mean that those features are not available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="platform-invoke-pinvoke"></a><span data-ttu-id="66e23-118">平台调用 (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="66e23-118">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="66e23-119">P/Invoke 是可用于从托管代码访问非托管库中的结构、回调和函数的一种技术。</span><span class="sxs-lookup"><span data-stu-id="66e23-119">P/Invoke is a technology that allows you to access structs, callbacks and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="66e23-120">大多数 P/Invoke API 包含在以下两个命名空间中：`System` 和 `System.Runtime.InteropServices`。</span><span class="sxs-lookup"><span data-stu-id="66e23-120">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="66e23-121">使用这两个命名空间可以访问用于描述如何与本机组件通信的特性。</span><span class="sxs-lookup"><span data-stu-id="66e23-121">Using these two namespaces will allow you access to the attributes that describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="66e23-122">我们从最常见的示例着手。该示例在托管代码中调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="66e23-122">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="66e23-123">让我们从命令行应用程序显示一个消息框：</span><span class="sxs-lookup"><span data-stu-id="66e23-123">Let’s show a message box from a command-line application:</span></span>

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

<span data-ttu-id="66e23-124">上述示例非常简单，但确实演示了从托管代码调用非托管函数需要做些什么。</span><span class="sxs-lookup"><span data-stu-id="66e23-124">The example above is pretty simple, but it does show off what is needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="66e23-125">让我们逐步分析该示例：</span><span class="sxs-lookup"><span data-stu-id="66e23-125">Let’s step through the example:</span></span>

*   <span data-ttu-id="66e23-126">第 1 行显示 `System.Runtime.InteropServices`（用于保存全部所需项的命名空间）的 using 语句。</span><span class="sxs-lookup"><span data-stu-id="66e23-126">Line #1 shows the using statement for the `System.Runtime.InteropServices` which is the namespace that holds all of the items we need.</span></span>
*   <span data-ttu-id="66e23-127">第 5 行引入 `DllImport` 特性。</span><span class="sxs-lookup"><span data-stu-id="66e23-127">Line #5 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="66e23-128">此特性至关重要，因为它告诉运行时要加载非托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="66e23-128">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="66e23-129">这也是我们要调用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="66e23-129">This is the DLL into which we wish to invoke.</span></span>
*   <span data-ttu-id="66e23-130">第 6 行显示了 P/Invoke 的关键作用。</span><span class="sxs-lookup"><span data-stu-id="66e23-130">Line #6 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="66e23-131">它定义了一个托管方法，该方法的签名与非托管方法**完全相同**。</span><span class="sxs-lookup"><span data-stu-id="66e23-131">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="66e23-132">可以看到，声明中包含一个新关键字 `extern`，告诉运行时这是一个外部方法。调用该方法时，运行时应在 `DllImport` 特性中指定的 DLL 内查找该方法。</span><span class="sxs-lookup"><span data-stu-id="66e23-132">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="66e23-133">该示例的剩余部分无非就是调用该方法，就像调用其他任何托管方法一样。</span><span class="sxs-lookup"><span data-stu-id="66e23-133">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="66e23-134">在 macOS 上也可以使用类似的示例。</span><span class="sxs-lookup"><span data-stu-id="66e23-134">The sample is similar for macOS.</span></span> <span data-ttu-id="66e23-135">当然，需要更改的一项设置就是 `DllImport` 特性中的库名称，因为 macOS 使用不同的方案来命名动态库。</span><span class="sxs-lookup"><span data-stu-id="66e23-135">One thing that needs to change is, of course, the name of the library in the `DllImport` attribute, as macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="66e23-136">下面的示例使用 `getpid(2)` 函数获取应用程序的进程 ID，然后控制台上列显该 ID。</span><span class="sxs-lookup"><span data-stu-id="66e23-136">The sample below uses the `getpid(2)` function to get the process ID of the application and print it out to the console.</span></span>

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

<span data-ttu-id="66e23-137">它在 Linux 上也是类似的。</span><span class="sxs-lookup"><span data-stu-id="66e23-137">It is also similar on Linux.</span></span> <span data-ttu-id="66e23-138">函数名称相同，因为 `getpid(2)` 是标准 [POSIX](https://en.wikipedia.org/wiki/POSIX) 系统调用。</span><span class="sxs-lookup"><span data-stu-id="66e23-138">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

### <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="66e23-139">从非托管代码调用托管代码</span><span class="sxs-lookup"><span data-stu-id="66e23-139">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="66e23-140">运行时允许通信流量双向流通，这样，你便可以使用函数指针从本机函数调用托管项目。</span><span class="sxs-lookup"><span data-stu-id="66e23-140">Of course, the runtime allows communication to flow both ways which enables you to call into managed artifacts from native functions, using function pointers.</span></span> <span data-ttu-id="66e23-141">在托管代码中，与函数指针最接近的功能就是**委托**，正是凭借这个功能，才能从本机代码回调托管代码。</span><span class="sxs-lookup"><span data-stu-id="66e23-141">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="66e23-142">此功能的使用方式类似于上面所述的从托管代码调用本机进程。</span><span class="sxs-lookup"><span data-stu-id="66e23-142">The way to use this feature is similar to managed to native process described above.</span></span> <span data-ttu-id="66e23-143">对于给定的回调，需要定义一个与签名匹配的委托，并将其传入外部方法。</span><span class="sxs-lookup"><span data-stu-id="66e23-143">For a given callback, you define a delegate that matches the signature, and pass that into the external method.</span></span> <span data-ttu-id="66e23-144">运行时将负责处理所有剩余工作。</span><span class="sxs-lookup"><span data-stu-id="66e23-144">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="66e23-145">在演练示例之前，最好是回顾一下所要使用的非托管函数的签名。</span><span class="sxs-lookup"><span data-stu-id="66e23-145">Before we walk through our example, it is good to go over the signatures of the unmanaged functions we need to work with.</span></span> <span data-ttu-id="66e23-146">要调用以枚举所有窗口的函数具有以下签名：`BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="66e23-146">The function we want to call to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="66e23-147">第一个参数是回调。</span><span class="sxs-lookup"><span data-stu-id="66e23-147">The first parameter is a callback.</span></span> <span data-ttu-id="66e23-148">该回调具有以下签名：`BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="66e23-148">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="66e23-149">了解签名后，让我们继续演练示例：</span><span class="sxs-lookup"><span data-stu-id="66e23-149">With this in mind, let’s walk through the example:</span></span>

*   <span data-ttu-id="66e23-150">示例中的第 8 行定义与非托管代码中回调签名匹配的委托。</span><span class="sxs-lookup"><span data-stu-id="66e23-150">Line #8 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="66e23-151">请注意如何在托管代码中使用 `IntPtr` 表示 LPARAM 和 HWND 类型。</span><span class="sxs-lookup"><span data-stu-id="66e23-151">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="66e23-152">第 10 和 11 行从 user32.dll 库中引入 `EnumWindows` 函数。</span><span class="sxs-lookup"><span data-stu-id="66e23-152">Lines #10 and #11 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="66e23-153">第 13 - 16 行实现该委托。</span><span class="sxs-lookup"><span data-stu-id="66e23-153">Lines #13 - 16 implement the delegate.</span></span> <span data-ttu-id="66e23-154">在这个简单的示例中，我们只要将句柄输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="66e23-154">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="66e23-155">最后，第 19 行调用外部方法并传入委托。</span><span class="sxs-lookup"><span data-stu-id="66e23-155">Finally, in line #19 we invoke the external method and pass in the delegate.</span></span>

<span data-ttu-id="66e23-156">下面显示了 Linux 和 macOS 示例。</span><span class="sxs-lookup"><span data-stu-id="66e23-156">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="66e23-157">在这些平台上，我们可以使用 C 库 `libc` 中的 `ftw` 函数。</span><span class="sxs-lookup"><span data-stu-id="66e23-157">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="66e23-158">此函数用于遍历目录层次结构，它使用指向某个函数的指针作为其参数之一。</span><span class="sxs-lookup"><span data-stu-id="66e23-158">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="66e23-159">该函数具有以下签名：`int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`。</span><span class="sxs-lookup"><span data-stu-id="66e23-159">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="66e23-160">macOS 示例使用相同的函数，唯一的差别在于 `DllImport` 特性的自变量，因为 macOS 将 `libc` 保留在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="66e23-160">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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

<span data-ttu-id="66e23-161">上面两个示例都依赖于参数，在这两种情况下，参数是作为托管类型提供的。</span><span class="sxs-lookup"><span data-stu-id="66e23-161">Both of the above examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="66e23-162">运行时将采取“适当的措施”，在另一个平台上将这些代码处理成等效的代码。</span><span class="sxs-lookup"><span data-stu-id="66e23-162">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="66e23-163">由于此过程对于编写优质本机互操作代码非常重要，接下来让我们看看运行时在_封送_类型时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="66e23-163">Since this process is really important to writing quality native interop code, let’s take a look at what happens when the runtime _marshals_ the types.</span></span>

## <a name="type-marshalling"></a><span data-ttu-id="66e23-164">类型封送</span><span class="sxs-lookup"><span data-stu-id="66e23-164">Type marshalling</span></span>

<span data-ttu-id="66e23-165">**封送**是当类型需要跨越托管边界进入本机代码（或反之）时转换类型的过程。</span><span class="sxs-lookup"><span data-stu-id="66e23-165">**Marshalling** is the process of transforming types when they need to cross the managed boundary into native and vice versa.</span></span>

<span data-ttu-id="66e23-166">需要封送的原因是托管代码与非托管代码中的类型并不相同。</span><span class="sxs-lookup"><span data-stu-id="66e23-166">The reason marshalling is needed is because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="66e23-167">例如，在托管代码中，可指定 `String`。但在非托管环境中，字符串类型可以是 Unicode（“宽型”）、非 Unicode、null 结尾、ASCII 等。默认情况下，P/Invoke 子系统会根据默认行为尽量采取适当的措施。相关信息请参阅 [MSDN](../../docs/framework/interop/default-marshaling-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="66e23-167">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem will try to do the Right Thing based on the default behavior which you can see on [MSDN](../../docs/framework/interop/default-marshaling-behavior.md).</span></span> <span data-ttu-id="66e23-168">但是，如果需要额外的控制，可以使用 `MarshalAs` 特性指定要在非托管端上使用哪种预期类型。</span><span class="sxs-lookup"><span data-stu-id="66e23-168">However, for those situations where you need extra control, you can employ the `MarshalAs` attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="66e23-169">例如，如果要将字符串作为以 null 结尾的 ANSI 字符串发送，可以执行类似于下面的操作：</span><span class="sxs-lookup"><span data-stu-id="66e23-169">For instance, if we want the string to be sent as a null-terminated ANSI string, we could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a><span data-ttu-id="66e23-170">封送类和结构</span><span class="sxs-lookup"><span data-stu-id="66e23-170">Marshalling classes and structs</span></span>

<span data-ttu-id="66e23-171">有关类型封送的另一个问题是如何将结构传入非托管方法。</span><span class="sxs-lookup"><span data-stu-id="66e23-171">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="66e23-172">例如，某些非托管方法需要使用结构作为参数。</span><span class="sxs-lookup"><span data-stu-id="66e23-172">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="66e23-173">在这种情况下，需要在环境的托管部分中创建相应的结构或类，以便将它用作参数。</span><span class="sxs-lookup"><span data-stu-id="66e23-173">In these cases, we need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="66e23-174">不过，仅仅是定义类并不足够，还需要告知封送拆收器如何将类中的字段映射到非托管结构。</span><span class="sxs-lookup"><span data-stu-id="66e23-174">However, just defining the class is not enough, we also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="66e23-175">这就是 `StructLayout` 特性的作用所在。</span><span class="sxs-lookup"><span data-stu-id="66e23-175">This is where the `StructLayout` attribute comes into play.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="66e23-176">上面这个简单的示例演示了如何调用 `GetSystemTime()` 函数。</span><span class="sxs-lookup"><span data-stu-id="66e23-176">The example above shows off a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="66e23-177">值得注意的部分是第 4 行。</span><span class="sxs-lookup"><span data-stu-id="66e23-177">The interesting bit is on line 4.</span></span> <span data-ttu-id="66e23-178">该属性指定应按顺序将类的字段映射到另一端（非托管端）上的结构。</span><span class="sxs-lookup"><span data-stu-id="66e23-178">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="66e23-179">这意味着，字段的命名并不重要，唯一重要的是字段顺序，因为这种顺序需对应于非托管结构，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66e23-179">This means that the naming of the fields is not important, only their order is important, as it needs to correspond to the unmanaged struct, shown below:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="66e23-180">前一示例中已经演示了如何在 Linux 和 macOS 上执行此过程。</span><span class="sxs-lookup"><span data-stu-id="66e23-180">We already saw the Linux and macOS example for this in the previous example.</span></span> <span data-ttu-id="66e23-181">下面再演示一次。</span><span class="sxs-lookup"><span data-stu-id="66e23-181">It is shown again below.</span></span>

```csharp
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
```

<span data-ttu-id="66e23-182">`StatClass` 类表示 UNIX 系统上的 `stat` 系统调用返回的结构。</span><span class="sxs-lookup"><span data-stu-id="66e23-182">The `StatClass` class represents a structure that is returned by the `stat` system call on UNIX systems.</span></span> <span data-ttu-id="66e23-183">它显示有关给定文件的信息。</span><span class="sxs-lookup"><span data-stu-id="66e23-183">It represents information about a given file.</span></span> <span data-ttu-id="66e23-184">上面的类是托管代码中的 stat 结构表示形式。</span><span class="sxs-lookup"><span data-stu-id="66e23-184">The class above is the stat struct representation in managed code.</span></span> <span data-ttu-id="66e23-185">同样，该类中的字段顺序必须与本机结构相同（可以在偏好的 UNIX 实现上的手册页中找到相关信息），并且这些字段的基础类型必须相同。</span><span class="sxs-lookup"><span data-stu-id="66e23-185">Again, the fields in the class have to be in the same order as the native struct (you can find these by perusing man pages on your favorite UNIX implementation) and they have to be of the same underlying type.</span></span>

## <a name="more-resources"></a><span data-ttu-id="66e23-186">更多资源</span><span class="sxs-lookup"><span data-stu-id="66e23-186">More resources</span></span>

*   <span data-ttu-id="66e23-187">[PInvoke.net wiki](https://www.pinvoke.net/) 是一个极佳的 Wiki 站点，其中提供了有关常用 Win32 API 以及如何调用这些 API 的信息。</span><span class="sxs-lookup"><span data-stu-id="66e23-187">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="66e23-188">MSDN 上的 P/Invoke</span><span class="sxs-lookup"><span data-stu-id="66e23-188">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="66e23-189">有关 P/Invoke 的 Mono 文档</span><span class="sxs-lookup"><span data-stu-id="66e23-189">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
