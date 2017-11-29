---
title: "ISymUnmanagedWriter::OpenScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="49d42-102">ISymUnmanagedWriter::OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="49d42-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="49d42-103">在当前方法中打开新的词法范围。</span><span class="sxs-lookup"><span data-stu-id="49d42-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="49d42-104">作用域成为新的当前范围和推送到堆栈的作用域。</span><span class="sxs-lookup"><span data-stu-id="49d42-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="49d42-105">作用域必须形成一个层次结构。</span><span class="sxs-lookup"><span data-stu-id="49d42-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="49d42-106">同级不允许重叠。</span><span class="sxs-lookup"><span data-stu-id="49d42-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d42-107">语法</span><span class="sxs-lookup"><span data-stu-id="49d42-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49d42-108">参数</span><span class="sxs-lookup"><span data-stu-id="49d42-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="49d42-109">[in]第一个指令在词法作用域，以字节为单位，从方法的开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="49d42-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="49d42-110">[out]指向的指针`ULONG32`接收范围标识符。</span><span class="sxs-lookup"><span data-stu-id="49d42-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49d42-111">返回值</span><span class="sxs-lookup"><span data-stu-id="49d42-111">Return Value</span></span>  
 <span data-ttu-id="49d42-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="49d42-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d42-113">备注</span><span class="sxs-lookup"><span data-stu-id="49d42-113">Remarks</span></span>  
 <span data-ttu-id="49d42-114">`ISymUnmanagedWriter::OpenScope`返回可以用于一个不透明的作用域标识符[isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)若要定义的作用域的起始和结束偏移量在更高版本时。</span><span class="sxs-lookup"><span data-stu-id="49d42-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="49d42-115">在这种情况下，偏移量传递给`ISymUnmanagedWriter::OpenScope`和[isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)将被忽略。</span><span class="sxs-lookup"><span data-stu-id="49d42-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="49d42-116">范围标识符是仅在当前方法中有效。</span><span class="sxs-lookup"><span data-stu-id="49d42-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d42-117">要求</span><span class="sxs-lookup"><span data-stu-id="49d42-117">Requirements</span></span>  
 <span data-ttu-id="49d42-118">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49d42-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d42-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49d42-119">See Also</span></span>  
 [<span data-ttu-id="49d42-120">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="49d42-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)