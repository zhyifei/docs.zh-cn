---
title: 将算法名称映射到加密类
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912868"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="7d82c-102">将算法名称映射到加密类</span><span class="sxs-lookup"><span data-stu-id="7d82c-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="7d82c-103">开发人员可通过以下四种方式使用 Windows SDK 创建加密对象:</span><span class="sxs-lookup"><span data-stu-id="7d82c-103">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="7d82c-104">使用**new**运算符创建对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="7d82c-105">通过对该算法的抽象类调用**create**方法, 创建实现特定加密算法的对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="7d82c-106">通过调用<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法, 创建实现特定加密算法的对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="7d82c-107">通过对该类型算法<xref:System.Security.Cryptography.SymmetricAlgorithm>的抽象类调用**create**方法 (如), 创建一个实现一类加密算法 (如对称块密码) 的对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="7d82c-108">例如, 假设开发人员想要计算一组字节的 SHA1 哈希。</span><span class="sxs-lookup"><span data-stu-id="7d82c-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="7d82c-109"><xref:System.Security.Cryptography>命名空间包含 SHA1 算法的两个实现, 一个纯粹的托管实现, 另一个包装 CryptoAPI。</span><span class="sxs-lookup"><span data-stu-id="7d82c-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="7d82c-110">开发人员可以通过调用**new**运算符来选择实例化特定的 SHA1 <xref:System.Security.Cryptography.SHA1Managed>实现 (如)。</span><span class="sxs-lookup"><span data-stu-id="7d82c-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="7d82c-111">但是, 如果公共语言运行时加载哪个类 (只要类实现 SHA1 哈希算法), 开发人员就可以通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>方法来创建对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7d82c-112">此方法调用**CryptoConfig. cryptoconfig.createfromname ("")** , 该方法必须返回 SHA1 哈希算法的一个实现。</span><span class="sxs-lookup"><span data-stu-id="7d82c-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="7d82c-113">开发人员还可以调用**CryptoConfig. cryptoconfig.createfromname ("SHA1")** , 因为默认情况下, 加密配置包括 .NET Framework 中附带的算法的短名称。</span><span class="sxs-lookup"><span data-stu-id="7d82c-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="7d82c-114">如果使用的哈希算法并不重要, 开发人员可以调用方法, <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>这将返回实现哈希转换的对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="7d82c-115">在配置文件中映射算法名称</span><span class="sxs-lookup"><span data-stu-id="7d82c-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="7d82c-116">默认情况下, 运行时为<xref:System.Security.Cryptography.SHA1CryptoServiceProvider>所有四个方案返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="7d82c-117">但是, 计算机管理员可以更改最后两个方案中的方法返回的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="7d82c-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="7d82c-118">为此, 必须将友好算法名称映射到要在计算机配置文件 (Machine.config) 中使用的类。</span><span class="sxs-lookup"><span data-stu-id="7d82c-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="7d82c-119">下面的示例演示如何配置运行时, 使其成为**CryptoConfig、CRYPTOCONFIG.CREATEFROMNAME ("SHA1")** 和 HashAlgorithm. 的配置运行时的配置。 **返回对象。** `MySHA1HashClass`</span><span class="sxs-lookup"><span data-stu-id="7d82c-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
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
  
 <span data-ttu-id="7d82c-120">您可以在[< 的 cryptoClass\>元素](./file-schema/cryptography/cryptoclass-element.md)中指定属性的名称 (上一个示例将属性`MySHA1Hash`命名为)。</span><span class="sxs-lookup"><span data-stu-id="7d82c-120">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="7d82c-121">CryptoClass > 元素中 **\<** 属性的值是公共语言运行时用来查找类的字符串。</span><span class="sxs-lookup"><span data-stu-id="7d82c-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="7d82c-122">您可以使用满足指定[完全限定的类型名称](../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="7d82c-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="7d82c-123">许多算法名称可以映射到同一个类。</span><span class="sxs-lookup"><span data-stu-id="7d82c-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="7d82c-124">Y > 元素将类映射到一个友好算法名称。 [ \<](./file-schema/cryptography/nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d82c-124">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="7d82c-125">**Name**属性可以是在调用**CryptoConfig. cryptoconfig.createfromname**方法时使用的字符串, 也可以是<xref:System.Security.Cryptography>命名空间中抽象加密类的名称。</span><span class="sxs-lookup"><span data-stu-id="7d82c-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="7d82c-126">**Class**特性的值是 **\<cryptoClass >** 元素中的特性的名称。</span><span class="sxs-lookup"><span data-stu-id="7d82c-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d82c-127">可以通过调用<xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>或**CryptoConfig. cryptoconfig.createfromname ("SHA1")** 方法获取 SHA1 算法。</span><span class="sxs-lookup"><span data-stu-id="7d82c-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="7d82c-128">每个方法仅保证返回实现 SHA1 算法的对象。</span><span class="sxs-lookup"><span data-stu-id="7d82c-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="7d82c-129">不需要将算法的每个友好名称映射到配置文件中的相同类。</span><span class="sxs-lookup"><span data-stu-id="7d82c-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="7d82c-130">有关默认名称及其映射到的类的列表, 请参阅<xref:System.Security.Cryptography.CryptoConfig>。</span><span class="sxs-lookup"><span data-stu-id="7d82c-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d82c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d82c-131">See also</span></span>

- [<span data-ttu-id="7d82c-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7d82c-132">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7d82c-133">配置加密类</span><span class="sxs-lookup"><span data-stu-id="7d82c-133">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
