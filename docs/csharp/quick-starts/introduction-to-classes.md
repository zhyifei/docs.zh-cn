---
title: "快速入门 - 类简介 - C# 指南"
description: "创建首个 C# 程序，并探索面向对象的概念"
author: billwagner
ms.author: wiwagn
ms.date: 10/11/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 0ddb7508841087571c0cd095b1d1518e4aad50ff
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2017
---
# <a name="introduction-to-classes"></a><span data-ttu-id="e968c-103">类简介</span><span class="sxs-lookup"><span data-stu-id="e968c-103">Introduction to classes</span></span>

<span data-ttu-id="e968c-104">若要更好地学习本课程，需要已安装 [.NET Core SDK](http://dot.net/core) 和选定编辑器。</span><span class="sxs-lookup"><span data-stu-id="e968c-104">This lesson assumes that you've installed [.NET Core SDK](http://dot.net/core), and an editor of your choice.</span></span> <span data-ttu-id="e968c-105">如果尚未安装，请尝试在 Mac 或 Windows 上使用 [Visual Studio Code](https://code.visualstudio.com/) 或 [Visual Studio](https://www.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="e968c-105">If you don't have one, try [Visual Studio Code](https://code.visualstudio.com/), or [Visual Studio](https://www.visualstudio.com/) on Mac or Windows.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="e968c-106">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="e968c-106">Create your application</span></span>

<span data-ttu-id="e968c-107">使用终端窗口，创建名为 classes 的目录。</span><span class="sxs-lookup"><span data-stu-id="e968c-107">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="e968c-108">可以在其中生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="e968c-108">You'll build your application there.</span></span> <span data-ttu-id="e968c-109">将此目录更改为当前目录，并在控制台窗口中键入 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="e968c-109">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="e968c-110">此命令可创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="e968c-110">This command creates your application.</span></span> <span data-ttu-id="e968c-111">打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="e968c-111">Open **Program.cs**.</span></span> <span data-ttu-id="e968c-112">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e968c-112">It should look like this:</span></span>

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

<span data-ttu-id="e968c-113">在本快速入门课程中，将要新建表示银行帐户的类型。</span><span class="sxs-lookup"><span data-stu-id="e968c-113">In this quick start, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="e968c-114">通常情况下，开发者都会在不同的文本文件中定义每个类。</span><span class="sxs-lookup"><span data-stu-id="e968c-114">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="e968c-115">这样可以更轻松地管理不断增大的程序。</span><span class="sxs-lookup"><span data-stu-id="e968c-115">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="e968c-116">在 classes 目录中，新建名为 BankAccount.cs 的文件。</span><span class="sxs-lookup"><span data-stu-id="e968c-116">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="e968c-117">此文件包含银行帐户定义。</span><span class="sxs-lookup"><span data-stu-id="e968c-117">This file will contain the deefinition of a ***bank account***.</span></span> <span data-ttu-id="e968c-118">面向对象的编程组织代码的方式为，创建类形式的类型。</span><span class="sxs-lookup"><span data-stu-id="e968c-118">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="e968c-119">这些类包含表示特定实体的代码。</span><span class="sxs-lookup"><span data-stu-id="e968c-119">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="e968c-120">`BankAccount` 类表示银行帐户。</span><span class="sxs-lookup"><span data-stu-id="e968c-120">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="e968c-121">代码通过方法和属性实现特定操作。</span><span class="sxs-lookup"><span data-stu-id="e968c-121">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="e968c-122">在本快速入门课程中，银行帐户支持以下行为：</span><span class="sxs-lookup"><span data-stu-id="e968c-122">In this quick start, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="e968c-123">用一个 10 位数唯一标识银行帐户。</span><span class="sxs-lookup"><span data-stu-id="e968c-123">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="e968c-124">用字符串存储一个或多个所有者名称。</span><span class="sxs-lookup"><span data-stu-id="e968c-124">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="e968c-125">可以检索余额。</span><span class="sxs-lookup"><span data-stu-id="e968c-125">The balance can be retrieved.</span></span>
1. <span data-ttu-id="e968c-126">接受存款。</span><span class="sxs-lookup"><span data-stu-id="e968c-126">It accepts deposits.</span></span>
1. <span data-ttu-id="e968c-127">接受取款。</span><span class="sxs-lookup"><span data-stu-id="e968c-127">It accepts withdrawals.</span></span>
1. <span data-ttu-id="e968c-128">初始余额必须是正数。</span><span class="sxs-lookup"><span data-stu-id="e968c-128">The initial balance must be positive.</span></span>
1. <span data-ttu-id="e968c-129">取款后的余额不能是负数。</span><span class="sxs-lookup"><span data-stu-id="e968c-129">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="e968c-130">定义银行帐户类型</span><span class="sxs-lookup"><span data-stu-id="e968c-130">Define the bank account type</span></span>

<span data-ttu-id="e968c-131">首先，创建定义此行为的类的基本设置。</span><span class="sxs-lookup"><span data-stu-id="e968c-131">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="e968c-132">具体如下所示：</span><span class="sxs-lookup"><span data-stu-id="e968c-132">It would look like this:</span></span>

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

        public void MakeWithdrawal(decimal amount, DateTime date, string payee, string note)
        {
        }
    }
}
```

<span data-ttu-id="e968c-133">继续操作前，先来看看已经生成的内容。</span><span class="sxs-lookup"><span data-stu-id="e968c-133">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="e968c-134">借助 `namespace` 声明，可以按逻辑组织代码。</span><span class="sxs-lookup"><span data-stu-id="e968c-134">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="e968c-135">本快速入门课程的篇幅较小，因此将所有代码都置于一个命名空间内。</span><span class="sxs-lookup"><span data-stu-id="e968c-135">This quick start is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="e968c-136">`public class BankAccount` 定义要创建的类或类型。</span><span class="sxs-lookup"><span data-stu-id="e968c-136">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="e968c-137">类声明后面 `{` 和 `}` 中的所有内容定义了类行为。</span><span class="sxs-lookup"><span data-stu-id="e968c-137">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="e968c-138">`BankAccount` 类有五个成员。</span><span class="sxs-lookup"><span data-stu-id="e968c-138">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="e968c-139">前三个成员是属性。</span><span class="sxs-lookup"><span data-stu-id="e968c-139">The first three are ***properties***.</span></span> <span data-ttu-id="e968c-140">属性是数据元素，可以包含强制执行验证或其他规则的代码。</span><span class="sxs-lookup"><span data-stu-id="e968c-140">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="e968c-141">最后两个成员是方法。</span><span class="sxs-lookup"><span data-stu-id="e968c-141">The last two are ***methods***.</span></span> <span data-ttu-id="e968c-142">方法是执行一个函数的代码块。</span><span class="sxs-lookup"><span data-stu-id="e968c-142">Methods are blocks of code that peform a single function.</span></span> <span data-ttu-id="e968c-143">读取每个成员的名称应该能够为自己或其他开发者提供了解类用途的足够信息。</span><span class="sxs-lookup"><span data-stu-id="e968c-143">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="e968c-144">打开新帐户</span><span class="sxs-lookup"><span data-stu-id="e968c-144">Open a new account</span></span>

<span data-ttu-id="e968c-145">要实现的第一个功能是打开银行帐户。</span><span class="sxs-lookup"><span data-stu-id="e968c-145">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="e968c-146">打开帐户时，客户必须提供初始余额，以及此帐户的一个或多个所有者的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e968c-146">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="e968c-147">新建 `BankAccount` 类型的对象意味着，定义可分配这些值的构造函数。</span><span class="sxs-lookup"><span data-stu-id="e968c-147">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="e968c-148">构造函数是与类同名的成员。</span><span class="sxs-lookup"><span data-stu-id="e968c-148">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="e968c-149">用于初始化相应类类型的对象。</span><span class="sxs-lookup"><span data-stu-id="e968c-149">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="e968c-150">将以下构造函数添加到 `BankAccount` 类型中：</span><span class="sxs-lookup"><span data-stu-id="e968c-150">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="e968c-151">构造函数是在使用 [`new`](../language-reference/keywords/new.md) 创建对象时进行调用。</span><span class="sxs-lookup"><span data-stu-id="e968c-151">Constructors are called when you create an object using [`new`](../language-reference/keywords/new.md).</span></span> <span data-ttu-id="e968c-152">将 program.cs 中的代码行 `Console.WriteLine("Hello World!");` 替换为以下代码行（将 `<name>` 替换为自己的名称）：</span><span class="sxs-lookup"><span data-stu-id="e968c-152">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="e968c-153">键入 `dotnet run`，看看会发生什么。</span><span class="sxs-lookup"><span data-stu-id="e968c-153">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="e968c-154">有没有注意到帐号为空？</span><span class="sxs-lookup"><span data-stu-id="e968c-154">Did you notice that the account number is blank?</span></span> <span data-ttu-id="e968c-155">是时候解决这个问题了。</span><span class="sxs-lookup"><span data-stu-id="e968c-155">It's time to fix that.</span></span> <span data-ttu-id="e968c-156">帐号应在构造对象时分配。</span><span class="sxs-lookup"><span data-stu-id="e968c-156">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="e968c-157">但不得由调用方负责创建。</span><span class="sxs-lookup"><span data-stu-id="e968c-157">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="e968c-158">`BankAccount` 类代码应了解如何分配新帐号。</span><span class="sxs-lookup"><span data-stu-id="e968c-158">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="e968c-159">这样做的简单方法是从一个 10 位数开始。</span><span class="sxs-lookup"><span data-stu-id="e968c-159">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="e968c-160">帐号随每个新建的帐户而递增。</span><span class="sxs-lookup"><span data-stu-id="e968c-160">Increment it when each new account is created.</span></span> <span data-ttu-id="e968c-161">最后，在构造对象时，存储当前的帐号。</span><span class="sxs-lookup"><span data-stu-id="e968c-161">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="e968c-162">将以下成员声明添加到 `BankAccount` 类中：</span><span class="sxs-lookup"><span data-stu-id="e968c-162">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="e968c-163">此为数据成员。</span><span class="sxs-lookup"><span data-stu-id="e968c-163">This is a data member.</span></span> <span data-ttu-id="e968c-164">它是 `private`，这意味着只能通过 `BankAccount` 类中的代码访问它。</span><span class="sxs-lookup"><span data-stu-id="e968c-164">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="e968c-165">这是一种分离公共责任（如拥有帐号）与私有实现（如何生成帐号）的方法。将下面两行代码添加到构造函数，以分配帐号：</span><span class="sxs-lookup"><span data-stu-id="e968c-165">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="e968c-166">键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="e968c-166">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="e968c-167">创建存款和取款</span><span class="sxs-lookup"><span data-stu-id="e968c-167">Create deposits and withdrawals</span></span>

<span data-ttu-id="e968c-168">银行帐户类必须接受存款和取款，才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="e968c-168">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="e968c-169">接下来，将为银行帐户创建每笔交易日记，实现存款和取款。</span><span class="sxs-lookup"><span data-stu-id="e968c-169">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="e968c-170">与仅更新每笔交易余额相比，这样做有一些优点。</span><span class="sxs-lookup"><span data-stu-id="e968c-170">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="e968c-171">历史记录可用于审核所有交易，并管理每日余额。</span><span class="sxs-lookup"><span data-stu-id="e968c-171">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="e968c-172">通过在需要时根据所有交易的历史记录计算余额，单笔交易中修正的任何错误将会在下次计算余额时得到正确体现。</span><span class="sxs-lookup"><span data-stu-id="e968c-172">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="e968c-173">接下来，先新建表示交易的类型。</span><span class="sxs-lookup"><span data-stu-id="e968c-173">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="e968c-174">这是一个没有任何责任的简单类型。</span><span class="sxs-lookup"><span data-stu-id="e968c-174">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="e968c-175">但需要有多个属性。</span><span class="sxs-lookup"><span data-stu-id="e968c-175">It needs a few properties.</span></span> <span data-ttu-id="e968c-176">新建名为 Transaction.cs 的文件。</span><span class="sxs-lookup"><span data-stu-id="e968c-176">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="e968c-177">向新文件添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="e968c-177">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="e968c-178">现在，将 `Transaction` 对象的 <xref:System.Collections.Generic.List%601> 添加到 `BankAccount` 类中。</span><span class="sxs-lookup"><span data-stu-id="e968c-178">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="e968c-179">添加以下声明：</span><span class="sxs-lookup"><span data-stu-id="e968c-179">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="e968c-180"><xref:System.Collections.Generic.List%601> 类要求导入不同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e968c-180">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="e968c-181">在 BankAccount.cs 的开头，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="e968c-181">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="e968c-182">现在，更改 `Balance` 的报告方式。</span><span class="sxs-lookup"><span data-stu-id="e968c-182">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="e968c-183">可以通过对所有交易的值进行求和计算余额。</span><span class="sxs-lookup"><span data-stu-id="e968c-183">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="e968c-184">将 `BankAccount` 类中 `Balance` 的声明修改为如下所示：</span><span class="sxs-lookup"><span data-stu-id="e968c-184">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="e968c-185">此示例反映了属性的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="e968c-185">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="e968c-186">现在，可以在其他程序员要求获取余额时计算值。</span><span class="sxs-lookup"><span data-stu-id="e968c-186">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="e968c-187">计算会枚举所有交易，总和即为当前余额。</span><span class="sxs-lookup"><span data-stu-id="e968c-187">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="e968c-188">接下来，实现 `MakeDeposit` 和 `MakeWithdrawal` 方法。</span><span class="sxs-lookup"><span data-stu-id="e968c-188">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="e968c-189">这些方法将强制执行最后两条规则：初始余额必须为正数，且取款后的余额不能是负数。</span><span class="sxs-lookup"><span data-stu-id="e968c-189">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="e968c-190">这就引入了异常的概念。</span><span class="sxs-lookup"><span data-stu-id="e968c-190">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="e968c-191">指明方法无法成功完成工作的标准方法是抛出异常。</span><span class="sxs-lookup"><span data-stu-id="e968c-191">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="e968c-192">异常类型及其关联消息描述了错误。</span><span class="sxs-lookup"><span data-stu-id="e968c-192">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="e968c-193">在此示例中，如果存款金额为负数，`MakeDeposit` 方法会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="e968c-193">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="e968c-194">如果取款金额为负数，或取款后的余额为负数，`MakeWithdrawal` 方法会抛出异常：</span><span class="sxs-lookup"><span data-stu-id="e968c-194">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="e968c-195">[`throw`](../language-reference/keywords/throw.md) 语句抛出异常。</span><span class="sxs-lookup"><span data-stu-id="e968c-195">The [`throw`](../language-reference/keywords/throw.md) statment **throws** an exception.</span></span> <span data-ttu-id="e968c-196">当前方法执行结束，并将在找到匹配的 `catch` 块时继续执行。</span><span class="sxs-lookup"><span data-stu-id="e968c-196">Execution of the current method ends, and will resume when a matching `catch` block is found.</span></span> <span data-ttu-id="e968c-197">添加 `catch` 块可以稍后再测试一下此代码。</span><span class="sxs-lookup"><span data-stu-id="e968c-197">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="e968c-198">构造函数应进行一处更改，更改为添加初始交易，而不是直接更新余额。</span><span class="sxs-lookup"><span data-stu-id="e968c-198">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="e968c-199">由于已编写 `MakeDeposit` 方法，因此通过构造函数调用它。</span><span class="sxs-lookup"><span data-stu-id="e968c-199">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="e968c-200">完成的构造函数应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e968c-200">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="e968c-201"><xref:System.DateTime.Now?displayProperty=nameWithType> 是返回当前日期和时间的属性。</span><span class="sxs-lookup"><span data-stu-id="e968c-201"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="e968c-202">在 `Main` 方法中添加几个存款和取款，对此进行测试：</span><span class="sxs-lookup"><span data-stu-id="e968c-202">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="e968c-203">接下来，尝试创建初始余额为负数的帐户，测试能否捕获到错误条件：</span><span class="sxs-lookup"><span data-stu-id="e968c-203">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try {
    var invalidAccount = new BankAccount("invalid", -55);
} catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="e968c-204">使用 [`try` 和 `catch` 语句](../language-reference/keywords/try-catch.md)，标记可能会抛出异常的代码块，并捕获预期错误。</span><span class="sxs-lookup"><span data-stu-id="e968c-204">You use the [`try` and `catch` statements](../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions, and to catch those errors that you expect.</span></span> <span data-ttu-id="e968c-205">可以使用相同的技术，测试代码能否在取款后的余额为负数时抛出异常：</span><span class="sxs-lookup"><span data-stu-id="e968c-205">You can use the same technique to test the code that throws for a negative balance:</span></span>

```csharp
// Test for a negative balance
try {
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
} catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="e968c-206">保存此文件，并键入 `dotnet run`，试运行看看。</span><span class="sxs-lookup"><span data-stu-id="e968c-206">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="e968c-207">挑战 - 记录所有交易</span><span class="sxs-lookup"><span data-stu-id="e968c-207">Challenge - log all transactions</span></span>

<span data-ttu-id="e968c-208">为了完成本快速入门课程，可以编写 `GetAccountHistory` 方法，为交易历史记录创建 `string`。</span><span class="sxs-lookup"><span data-stu-id="e968c-208">To finish this quick start, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="e968c-209">将此方法添加到 `BankAccount` 类型中：</span><span class="sxs-lookup"><span data-stu-id="e968c-209">add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="e968c-210">上面的代码使用 <xref:System.Text.StringBuilder> 类，设置包含每个交易行的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="e968c-210">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="e968c-211">在前面的快速入门课程中，也遇到过字符串格式设置代码。</span><span class="sxs-lookup"><span data-stu-id="e968c-211">You've seen the string formatting code earlier in these quick starts.</span></span> <span data-ttu-id="e968c-212">新增的一个字符为 `\t`。</span><span class="sxs-lookup"><span data-stu-id="e968c-212">One new character is `\t`.</span></span> <span data-ttu-id="e968c-213">这用于插入选项卡，从而设置输出格式。</span><span class="sxs-lookup"><span data-stu-id="e968c-213">That inserts a tab to format the output.</span></span>

<span data-ttu-id="e968c-214">添加以下代码行，在 Program.cs 中对它进行测试：</span><span class="sxs-lookup"><span data-stu-id="e968c-214">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="e968c-215">键入 `dotnet run` 看看结果如何。</span><span class="sxs-lookup"><span data-stu-id="e968c-215">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e968c-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e968c-216">Next Steps</span></span>

<span data-ttu-id="e968c-217">如果遇到问题，可以在 [GitHub 存储库](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)中查看本快速入门课程的源代码</span><span class="sxs-lookup"><span data-stu-id="e968c-217">If you got stuck, you can see the source for this quick start [in our GitHub repo](https://github.com/dotnet/docs/tree/master/samples/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="e968c-218">恭喜！已完成所有快速入门课程。</span><span class="sxs-lookup"><span data-stu-id="e968c-218">Congratulations, you've finished all our Quick Starts.</span></span> <span data-ttu-id="e968c-219">若要了解详细信息，请学习我们的[教程](../tutorials/index.md)</span><span class="sxs-lookup"><span data-stu-id="e968c-219">If you're eager to learn more, try our [tutorials](../tutorials/index.md)</span></span>
