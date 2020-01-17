---
title: .NET Core 上不支持的 API
description: 了解 .NET Framework 中始终在 .NET Core 上引发异常的 API。
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901342"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a>始终在 .NET Core 上引发异常的 API

以下 API 在指定平台的 .NET Core 上运行时将始终通过 <xref:System.PlatformNotSupportedException>。

本文按命名空间组织受影响的 API 成员。

> [!NOTE]
>
> - 本文是当前正在进行的工作。 它不是在 .NET Core 上引发异常的 API 的完整列表。
> - 本文不包括在 .NET Core 上引发的二进制序列化的显式接口实现。 有关详细信息，请参阅 [.NET Core 中的二进制序列化](../../standard/serialization/binary-serialization.md#net-core)。

## <a name="system"></a>System

| 成员 | Platform |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | 全部 |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | 全部 |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | 全部 |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | 全部 |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | 全部 |

## <a name="systemcodedomcompiler"></a>System.CodeDom.Compiler

| 成员 | Platform |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | 全部 |

## <a name="systemcollectionsspecialized"></a>System.Collections.Specialized

| 成员 | Platform |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | 全部 |

## <a name="systemconfiguration"></a>System.Configuration

| 成员 | Platform |
| - | - |
| <xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>（所有成员） | 全部 |

## <a name="systemconsole"></a>System.Console

| 成员 | Platform |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Console.BufferHeight?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.BufferWidth?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.CursorSize?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.CursorVisible?displayProperty=nameWithType>（仅获取） | Linux 和 macOS |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Console.Title?displayProperty=nameWithType>（仅获取） | Linux 和 macOS |
| <xref:System.Console.WindowHeight?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.WindowLeft?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.WindowTop?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Console.WindowWidth?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |

## <a name="systemdatacommon"></a>System.Data.Common

| 成员 | Platform |
| - | - |
| <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>（引发 <xref:System.NotSupportedException>） | 全部 |

## <a name="systemdiagnosticsprocess"></a>System.Diagnostics.Process

| 成员 | Platform |
| - | - |
| <xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>（仅设置） | Linux |
| <xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>（仅设置） | Linux |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | macOS |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅获取） | macOS |
| <xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |

## <a name="systemio"></a>System.IO

| 成员 | Platform |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemiopipes"></a>System.IO.Pipes

| 成员 | Platform |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>（仅设置） | Linux 和 macOS |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | Linux 和 macOS |

## <a name="systemmedia"></a>System.Media

| 成员 | Platform |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemnet"></a>System.Net

| 成员 | Platform |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemnetnetworkinformation"></a>System.Net.NetworkInformation

| 成员 | Platform |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | Windows (UWP) |

## <a name="systemnetsockets"></a>System.Net.Sockets

| 成员 | Platform |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | 全部 |

## <a name="systemnetwebsockets"></a>System.Net.WebSockets

| 成员 | Platform |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | 全部 |

## <a name="systemreflection"></a>System.Reflection

| 成员 | Platform |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | 全部 |

## <a name="systemruntimecompilerservices"></a>System.Runtime.CompilerServices

| 成员 | Platform |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | 全部 |

## <a name="systemruntimeinteropservices"></a>System.Runtime.InteropServices

| 成员 | Platform |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | 全部 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | 全部 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | 全部 |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | 全部 |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | Linux 和 macOS |

## <a name="systemruntimeserialization"></a>System.Runtime.Serialization

| 成员 | Platform |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | 全部 |

## <a name="systemsecurity"></a>System.Security

| 成员 | Platform |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | 全部 |

## <a name="systemsecurityclaims"></a>System.Security.Claims

| 成员 | Platform |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemsecuritycryptography"></a>System.Security.Cryptography

| 成员 | Platform |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | Linux 和 macOS |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | 全部 |

## <a name="systemsecuritycryptographypkcs"></a>System.Security.Cryptography.Pkcs

| 成员 | Platform |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | 全部 |

## <a name="systemsecuritycryptographyx509certificates"></a>System.Security.Cryptography.X509Certificates

| 成员 | Platform |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>（仅设置） | 全部 |

## <a name="systemsecurityauthenticationextendedprotection"></a>System.Security.Authentication.ExtendedProtection

| 成员 | Platform |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemsecuritypolicy"></a>System.Security.Policy

| 成员 | Platform |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemserviceprocessservicecontroller"></a>System.ServiceProcess.ServiceController

| 成员 | Platform |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |

## <a name="systemtextregularexpressions"></a>System.Text.RegularExpressions

| 成员 | Platform |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | 全部 |

## <a name="systemthreading"></a>System.Threading

| 成员 | Platform |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | 全部 |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | 全部 |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | 全部 |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | 全部 |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | 全部 |

## <a name="systemxml"></a>System.Xml

| 成员 | Platform |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | 全部 |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | 全部 |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | 全部 |

## <a name="see-also"></a>请参阅

- [从 .NET Framework 迁移到 .NET Core 的中断性变更](../compatibility/fx-core.md)
- [.NET Core 中的二进制序列化](../../standard/serialization/binary-serialization.md#net-core)
- [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)
