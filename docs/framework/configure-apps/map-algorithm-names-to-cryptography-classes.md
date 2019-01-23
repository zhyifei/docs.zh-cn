---
title: 将算法名称映射到加密类
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 87b428fffac98b4490a67e4713b56ec6e8fdcfe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569188"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="a8e08-102">将算法名称映射到加密类</span><span class="sxs-lookup"><span data-stu-id="a8e08-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="a8e08-103">有四种方法，开发人员可以创建加密对象使用[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a8e08-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="a8e08-104">使用创建对象**新**运算符。</span><span class="sxs-lookup"><span data-stu-id="a8e08-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="a8e08-105">创建一个对象，通过调用来实现特定加密算法**创建**的抽象类上为该算法的方法。</span><span class="sxs-lookup"><span data-stu-id="a8e08-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="a8e08-106">创建一个对象，通过调用来实现特定加密算法<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="a8e08-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a8e08-107">创建一个对象，通过调用实现加密算法 （如一种对称块密码） 的类**创建**方法的抽象类上为该类型的算法 (如<xref:System.Security.Cryptography.SymmetricAlgorithm>)。</span><span class="sxs-lookup"><span data-stu-id="a8e08-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="a8e08-108">例如，假设开发人员想要计算的一组字节的 SHA1 哈希。</span><span class="sxs-lookup"><span data-stu-id="a8e08-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="a8e08-109"><xref:System.Security.Cryptography>命名空间包含的 SHA1 算法、 一种纯托管的实现和一个包装 CryptoAPI 的两种实现。</span><span class="sxs-lookup"><span data-stu-id="a8e08-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="a8e08-110">开发人员可以选择要实例化特定 SHA1 实现 (如<xref:System.Security.Cryptography.SHA1Managed>) 通过调用**新**运算符。</span><span class="sxs-lookup"><span data-stu-id="a8e08-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="a8e08-111">但是，如果并不重要，只要类实现的 SHA1 哈希算法，公共语言运行时将加载哪些类，开发人员可以创建一个对象通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="a8e08-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a8e08-112">此方法调用**System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**，其必须返回的 SHA1 哈希算法的实现。</span><span class="sxs-lookup"><span data-stu-id="a8e08-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="a8e08-113">开发人员还可以调用**System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** 因为默认情况下，加密配置包括在.NET Framework 中提供的算法的短名称。</span><span class="sxs-lookup"><span data-stu-id="a8e08-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="a8e08-114">如果并不重要的哈希算法使用，开发人员可以调用<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>方法，它将返回实现哈希转换的对象。</span><span class="sxs-lookup"><span data-stu-id="a8e08-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="a8e08-115">在配置文件中的算法名称映射</span><span class="sxs-lookup"><span data-stu-id="a8e08-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="a8e08-116">默认情况下，运行时将返回<xref:System.Security.Cryptography.SHA1CryptoServiceProvider>所有四种方案的对象。</span><span class="sxs-lookup"><span data-stu-id="a8e08-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="a8e08-117">但是，计算机管理员可以更改的最后两个方案中的方法返回的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="a8e08-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="a8e08-118">若要执行此操作，必须将友好算法名称映射到你想要使用计算机配置文件 (Machine.config) 中的类中。</span><span class="sxs-lookup"><span data-stu-id="a8e08-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="a8e08-119">下面的示例演示如何配置运行时，以便**System.Security.Cryptography.SHA1.Create**， **System.Security.CryptoConfig.CreateFromName("SHA1")**，和**System.Security.Cryptography.HashAlgorithm.Create**返回`MySHA1HashClass`对象。</span><span class="sxs-lookup"><span data-stu-id="a8e08-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="a8e08-120">可以指定的名称中的属性[< cryptoClass\>元素](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)(前面的示例将该特性命名`MySHA1Hash`)。</span><span class="sxs-lookup"><span data-stu-id="a8e08-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="a8e08-121">中的属性的值 **\<cryptoClass >** 元素是一个字符串，公共语言运行时使用找到的类。</span><span class="sxs-lookup"><span data-stu-id="a8e08-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="a8e08-122">可以使用任何字符串都满足中指定的要求[指定完全限定的类型名称](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e08-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="a8e08-123">许多将算法名称可以映射到同一个类。</span><span class="sxs-lookup"><span data-stu-id="a8e08-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="a8e08-124">[ \<NameEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)将类映射到一个友好算法名称。</span><span class="sxs-lookup"><span data-stu-id="a8e08-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="a8e08-125">**名称**属性可以是调用时使用的是一个字符串**System.Security.Cryptography.CryptoConfig.CreateFromName**方法或抽象加密类中的名称<xref:System.Security.Cryptography>命名空间。</span><span class="sxs-lookup"><span data-stu-id="a8e08-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="a8e08-126">值**类**特性是中的属性的名称 **\<cryptoClass >** 元素。</span><span class="sxs-lookup"><span data-stu-id="a8e08-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8e08-127">可以通过调用获取 SHA1 算法<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>或**Security.CryptoConfig.CreateFromName("SHA1")** 方法。</span><span class="sxs-lookup"><span data-stu-id="a8e08-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="a8e08-128">它返回一个对象，用于实现 SHA1 算法，每个方法可仅保证。</span><span class="sxs-lookup"><span data-stu-id="a8e08-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="a8e08-129">无需将一种算法的每个友好名称映射到配置文件中的同一个类。</span><span class="sxs-lookup"><span data-stu-id="a8e08-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="a8e08-130">默认名称和它们映射到的类的列表，请参阅<xref:System.Security.Cryptography.CryptoConfig>。</span><span class="sxs-lookup"><span data-stu-id="a8e08-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e08-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8e08-131">See also</span></span>
- [<span data-ttu-id="a8e08-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="a8e08-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="a8e08-133">配置加密类</span><span class="sxs-lookup"><span data-stu-id="a8e08-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
