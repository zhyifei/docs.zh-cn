---
title: 类和对象 - C# 简介教程
description: 创建首个 C# 程序，并探索面向对象的概念
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 6ce0c86a4b746b8ea2db82899a82734a68e46957
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066060"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="a404d-103">使用类和对象探索面向对象的编程</span><span class="sxs-lookup"><span data-stu-id="a404d-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="a404d-104">本教程要求你有一台可用于开发的计算机。</span><span class="sxs-lookup"><span data-stu-id="a404d-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="a404d-105">.NET 主题 [10 分钟入门](https://www.microsoft.com/net/core)介绍了如何在 Mac、PC 或 Linux 上设置本地开发环境。</span><span class="sxs-lookup"><span data-stu-id="a404d-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="a404d-106">[熟悉开发工具](local-environment.md)不仅简要概述了将用到的命令，还收录了详细信息链接。</span><span class="sxs-lookup"><span data-stu-id="a404d-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="a404d-107">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="a404d-107">Create your application</span></span>

<span data-ttu-id="a404d-108">使用终端窗口，创建名为 classes 的目录。</span><span class="sxs-lookup"><span data-stu-id="a404d-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="a404d-109">可以在其中生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="a404d-109">You'll build your application there.</span></span> <span data-ttu-id="a404d-110">将此目录更改为当前目录，并在控制台窗口中键入 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="a404d-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="a404d-111">此命令可创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="a404d-111">This command creates your application.</span></span> <span data-ttu-id="a404d-112">打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="a404d-112">Open **Program.cs**.</span></span> <span data-ttu-id="a404d-113">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="a404d-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="a404d-114">在本教程中，将要新建表示银行帐户的类型。</span><span class="sxs-lookup"><span data-stu-id="a404d-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="a404d-115">通常情况下，开发者都会在不同的文本文件中定义每个类。</span><span class="sxs-lookup"><span data-stu-id="a404d-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="a404d-116">这样可以更轻松地管理不断增大的程序。</span><span class="sxs-lookup"><span data-stu-id="a404d-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="a404d-117">在 classes 目录中，新建名为 BankAccount.cs 的文件。</span><span class="sxs-lookup"><span data-stu-id="a404d-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="a404d-118">此文件包含“银行帐户”定义。</span><span class="sxs-lookup"><span data-stu-id="a404d-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="a404d-119">面向对象的编程组织代码的方式为，创建类形式的类型。</span><span class="sxs-lookup"><span data-stu-id="a404d-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="a404d-120">这些类包含表示特定实体的代码。</span><span class="sxs-lookup"><span data-stu-id="a404d-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="a404d-121">`BankAccount` 类表示银行帐户。</span><span class="sxs-lookup"><span data-stu-id="a404d-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="a404d-122">代码通过方法和属性实现特定操作。</span><span class="sxs-lookup"><span data-stu-id="a404d-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="a404d-123">在本教程中，银行帐户支持以下行为：</span><span class="sxs-lookup"><span data-stu-id="a404d-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="a404d-124">用一个 10 位数唯一标识银行帐户。</span><span class="sxs-lookup"><span data-stu-id="a404d-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="a404d-125">用字符串存储一个或多个所有者名称。</span><span class="sxs-lookup"><span data-stu-id="a404d-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="a404d-126">可以检索余额。</span><span class="sxs-lookup"><span data-stu-id="a404d-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="a404d-127">接受存款。</span><span class="sxs-lookup"><span data-stu-id="a404d-127">It accepts deposits.</span></span>
1. <span data-ttu-id="a404d-128">接受取款。</span><span class="sxs-lookup"><span data-stu-id="a404d-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="a404d-129">初始余额必须是正数。</span><span class="sxs-lookup"><span data-stu-id="a404d-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="a404d-130">取款后的余额不能是负数。</span><span class="sxs-lookup"><span data-stu-id="a404d-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="a404d-131">定义银行帐户类型</span><span class="sxs-lookup"><span data-stu-id="a404d-131">Define the bank account type</span></span>

<span data-ttu-id="a404d-132">首先，创建定义此行为的类的基本设置。</span><span class="sxs-lookup"><span data-stu-id="a404d-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="a404d-133">具体如下所示：</span><span class="sxs-lookup"><span data-stu-id="a404d-133">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="a404d-134">继续操作前，先来看看已经生成的内容。</span><span class="sxs-lookup"><span data-stu-id="a404d-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="a404d-135">借助 `namespace` 声明，可以按逻辑组织代码。</span><span class="sxs-lookup"><span data-stu-id="a404d-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="a404d-136">由于本教程的篇幅较小，因此所有代码都将添加到一个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="a404d-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="a404d-137">`public class BankAccount` 定义要创建的类或类型。</span><span class="sxs-lookup"><span data-stu-id="a404d-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="a404d-138">类声明后面 `{` 和 `}` 中的所有内容定义了类行为。</span><span class="sxs-lookup"><span data-stu-id="a404d-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="a404d-139">`BankAccount` 类有五个成员。</span><span class="sxs-lookup"><span data-stu-id="a404d-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="a404d-140">前三个成员是属性。</span><span class="sxs-lookup"><span data-stu-id="a404d-140">The first three are ***properties***.</span></span> <span data-ttu-id="a404d-141">属性是数据元素，可以包含强制执行验证或其他规则的代码。</span><span class="sxs-lookup"><span data-stu-id="a404d-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="a404d-142">最后两个成员是方法。</span><span class="sxs-lookup"><span data-stu-id="a404d-142">The last two are ***methods***.</span></span> <span data-ttu-id="a404d-143">方法是执行一个函数的代码块。</span><span class="sxs-lookup"><span data-stu-id="a404d-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="a404d-144">读取每个成员的名称应该能够为自己或其他开发者提供了解类用途的足够信息。</span><span class="sxs-lookup"><span data-stu-id="a404d-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="a404d-145">打开新帐户</span><span class="sxs-lookup"><span data-stu-id="a404d-145">Open a new account</span></span>

<span data-ttu-id="a404d-146">要实现的第一个功能是打开银行帐户。</span><span class="sxs-lookup"><span data-stu-id="a404d-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="a404d-147">打开帐户时，客户必须提供初始余额，以及此帐户的一个或多个所有者的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a404d-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="a404d-148">新建 `BankAccount` 类型的对象意味着，定义可分配这些值的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a404d-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="a404d-149">构造函数是与类同名的成员。</span><span class="sxs-lookup"><span data-stu-id="a404d-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="a404d-150">用于初始化相应类类型的对象。</span><span class="sxs-lookup"><span data-stu-id="a404d-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="a404d-151">将以下构造函数添加到 `BankAccount` 类型中：</span><span class="sxs-lookup"><span data-stu-id="a404d-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="a404d-152">构造函数是在使用 [`new`](../../language-reference/keywords/new.md) 创建对象时进行调用。</span><span class="sxs-lookup"><span data-stu-id="a404d-152">Constructors are called when you create an object using [`new`](../../language-reference/keywords/new.md).</span></span> <span data-ttu-id="a404d-153">将 program.cs 中的代码行 `Console.WriteLine("Hello World!");` 替换为以下代码行（将 `<name>` 替换为自己的名称）：</span><span class="sxs-lookup"><span data-stu-id="a404d-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="a404d-154">键入 `dotnet run`，看看会发生什么。</span><span class="sxs-lookup"><span data-stu-id="a404d-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="a404d-155">有没有注意到帐号为空？</span><span class="sxs-lookup"><span data-stu-id="a404d-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="a404d-156">是时候解决这个问题了。</span><span class="sxs-lookup"><span data-stu-id="a404d-156">It's time to fix that.</span></span> <span data-ttu-id="a404d-157">帐号应在构造对象时分配。</span><span class="sxs-lookup"><span data-stu-id="a404d-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="a404d-158">但不得由调用方负责创建。</span><span class="sxs-lookup"><span data-stu-id="a404d-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="a404d-159">`BankAccount` 类代码应了解如何分配新帐号。</span><span class="sxs-lookup"><span data-stu-id="a404d-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="a404d-160">这样做的简单方法是从一个 10 位数开始。</span><span class="sxs-lookup"><span data-stu-id="a404d-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="a404d-161">帐号随每个新建的帐户而递增。</span><span class="sxs-lookup"><span data-stu-id="a404d-161">Increment it when each new account is created.</span></span> <span data-ttu-id="a404d-162">最后，在构造对象时，存储当前的帐号。</span><span class="sxs-lookup"><span data-stu-id="a404d-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="a404d-163">将以下成员声明添加到 `BankAccount` 类中：</span><span class="sxs-lookup"><span data-stu-id="a404d-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="a404d-164">此为数据成员。</span><span class="sxs-lookup"><span data-stu-id="a404d-164">This is a data member.</span></span> <span data-ttu-id="a404d-165">它是 `private`，这意味着只能通过 `BankAccount` 类中的代码访问它。</span><span class="sxs-lookup"><span data-stu-id="a404d-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="a404d-166">这是一种分离公共责任（如拥有帐号）与私有实现（如何生成帐号）的方法。它也是 `static`，这意味着它由所有 `BankAccount` 对象共享。</span><span class="sxs-lookup"><span data-stu-id="a404d-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) It is also `static`, which means it is shared by all of the `BankAccount` objects.</span></span> <span data-ttu-id="a404d-167">非静态变量的值对于 `BankAccount` 对象的每个实例是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a404d-167">The value of a non-static variable is unique to each instance of the `BankAccount` object.</span></span> <span data-ttu-id="a404d-168">将下面两行代码添加到构造函数，以分配帐号：</span><span class="sxs-lookup"><span data-stu-id="a404d-168">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="a404d-169">键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="a404d-169">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="a404d-170">创建存款和取款</span><span class="sxs-lookup"><span data-stu-id="a404d-170">Create deposits and withdrawals</span></span>

<span data-ttu-id="a404d-171">银行帐户类必须接受存款和取款，才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="a404d-171">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="a404d-172">接下来，将为银行帐户创建每笔交易日记，实现存款和取款。</span><span class="sxs-lookup"><span data-stu-id="a404d-172">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="a404d-173">与仅更新每笔交易余额相比，这样做有一些优点。</span><span class="sxs-lookup"><span data-stu-id="a404d-173">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="a404d-174">历史记录可用于审核所有交易，并管理每日余额。</span><span class="sxs-lookup"><span data-stu-id="a404d-174">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="a404d-175">通过在需要时根据所有交易的历史记录计算余额，单笔交易中修正的任何错误将会在下次计算余额时得到正确体现。</span><span class="sxs-lookup"><span data-stu-id="a404d-175">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="a404d-176">接下来，先新建表示交易的类型。</span><span class="sxs-lookup"><span data-stu-id="a404d-176">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="a404d-177">这是一个没有任何责任的简单类型。</span><span class="sxs-lookup"><span data-stu-id="a404d-177">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="a404d-178">但需要有多个属性。</span><span class="sxs-lookup"><span data-stu-id="a404d-178">It needs a few properties.</span></span> <span data-ttu-id="a404d-179">新建名为 Transaction.cs 的文件。</span><span class="sxs-lookup"><span data-stu-id="a404d-179">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="a404d-180">向新文件添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="a404d-180">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="a404d-181">现在，将 `Transaction` 对象的 <xref:System.Collections.Generic.List%601> 添加到 `BankAccount` 类中。</span><span class="sxs-lookup"><span data-stu-id="a404d-181">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="a404d-182">添加以下声明：</span><span class="sxs-lookup"><span data-stu-id="a404d-182">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="a404d-183"><xref:System.Collections.Generic.List%601> 类要求导入不同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a404d-183">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="a404d-184">在 BankAccount.cs 的开头，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="a404d-184">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="a404d-185">现在，更改 `Balance` 的报告方式。</span><span class="sxs-lookup"><span data-stu-id="a404d-185">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="a404d-186">可以通过对所有交易的值进行求和计算余额。</span><span class="sxs-lookup"><span data-stu-id="a404d-186">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="a404d-187">将 `BankAccount` 类中 `Balance` 的声明修改为如下所示：</span><span class="sxs-lookup"><span data-stu-id="a404d-187">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="a404d-188">此示例反映了属性的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="a404d-188">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="a404d-189">现在，可以在其他程序员要求获取余额时计算值。</span><span class="sxs-lookup"><span data-stu-id="a404d-189">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="a404d-190">计算会枚举所有交易，总和即为当前余额。</span><span class="sxs-lookup"><span data-stu-id="a404d-190">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="a404d-191">接下来，实现 `MakeDeposit` 和 `MakeWithdrawal` 方法。</span><span class="sxs-lookup"><span data-stu-id="a404d-191">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="a404d-192">这些方法将强制执行最后两条规则：初始余额必须为正数，且取款后的余额不能是负数。</span><span class="sxs-lookup"><span data-stu-id="a404d-192">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="a404d-193">这就引入了异常的概念。</span><span class="sxs-lookup"><span data-stu-id="a404d-193">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="a404d-194">指明方法无法成功完成工作的标准方法是抛出异常。</span><span class="sxs-lookup"><span data-stu-id="a404d-194">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="a404d-195">异常类型及其关联消息描述了错误。</span><span class="sxs-lookup"><span data-stu-id="a404d-195">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="a404d-196">在此示例中，如果存款金额为负数，`MakeDeposit` 方法会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="a404d-196">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="a404d-197">如果取款金额为负数，或取款后的余额为负数，`MakeWithdrawal` 方法会抛出异常：</span><span class="sxs-lookup"><span data-stu-id="a404d-197">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="a404d-198">[`throw`](../../language-reference/keywords/throw.md) 语句将引发异常。</span><span class="sxs-lookup"><span data-stu-id="a404d-198">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="a404d-199">当前块执行结束，将控制权移交给在调用堆栈中发现的第一个匹配的 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="a404d-199">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="a404d-200">添加 `catch` 块可以稍后再测试一下此代码。</span><span class="sxs-lookup"><span data-stu-id="a404d-200">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="a404d-201">构造函数应进行一处更改，更改为添加初始交易，而不是直接更新余额。</span><span class="sxs-lookup"><span data-stu-id="a404d-201">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="a404d-202">由于已编写 `MakeDeposit` 方法，因此通过构造函数调用它。</span><span class="sxs-lookup"><span data-stu-id="a404d-202">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="a404d-203">完成的构造函数应如下所示：</span><span class="sxs-lookup"><span data-stu-id="a404d-203">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="a404d-204"><xref:System.DateTime.Now?displayProperty=nameWithType> 是返回当前日期和时间的属性。</span><span class="sxs-lookup"><span data-stu-id="a404d-204"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="a404d-205">在 `Main` 方法中添加几个存款和取款，对此进行测试：</span><span class="sxs-lookup"><span data-stu-id="a404d-205">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="a404d-206">接下来，尝试创建初始余额为负数的帐户，测试能否捕获到错误条件：</span><span class="sxs-lookup"><span data-stu-id="a404d-206">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="a404d-207">使用 [`try` 和 `catch` 语句](../../language-reference/keywords/try-catch.md)，标记可能会引发异常的代码块，并捕获预期错误。</span><span class="sxs-lookup"><span data-stu-id="a404d-207">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="a404d-208">可以使用相同的技术，测试代码能否在取款后的余额为负数时引发异常：</span><span class="sxs-lookup"><span data-stu-id="a404d-208">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

```csharp
// Test for a negative balance
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="a404d-209">保存此文件，并键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="a404d-209">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="a404d-210">挑战 - 记录所有交易</span><span class="sxs-lookup"><span data-stu-id="a404d-210">Challenge - log all transactions</span></span>

<span data-ttu-id="a404d-211">为了完成本教程，可以编写 `GetAccountHistory` 方法，为交易历史记录创建 `string`。</span><span class="sxs-lookup"><span data-stu-id="a404d-211">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="a404d-212">将此方法添加到 `BankAccount` 类型中：</span><span class="sxs-lookup"><span data-stu-id="a404d-212">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="a404d-213">上面的代码使用 <xref:System.Text.StringBuilder> 类，设置包含每个交易行的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="a404d-213">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="a404d-214">在前面的教程中，也遇到过字符串格式设置代码。</span><span class="sxs-lookup"><span data-stu-id="a404d-214">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="a404d-215">新增的一个字符为 `\t`。</span><span class="sxs-lookup"><span data-stu-id="a404d-215">One new character is `\t`.</span></span> <span data-ttu-id="a404d-216">这用于插入选项卡，从而设置输出格式。</span><span class="sxs-lookup"><span data-stu-id="a404d-216">That inserts a tab to format the output.</span></span>

<span data-ttu-id="a404d-217">添加以下代码行，在 Program.cs 中对它进行测试：</span><span class="sxs-lookup"><span data-stu-id="a404d-217">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="a404d-218">键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="a404d-218">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a404d-219">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a404d-219">Next Steps</span></span>

<span data-ttu-id="a404d-220">如果遇到问题，可以在 [GitHub 存储库](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)中查看本教程的源代码</span><span class="sxs-lookup"><span data-stu-id="a404d-220">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="a404d-221">恭喜，你已完成我们的所有 C# 简介教程。</span><span class="sxs-lookup"><span data-stu-id="a404d-221">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="a404d-222">若要了解详细信息，请继续学习我们的[教程](../index.md)</span><span class="sxs-lookup"><span data-stu-id="a404d-222">If you're eager to learn more, try more of our [tutorials](../index.md)</span></span>
