---
title: "_aligned_offset_realloc_dbg"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - _aligned_offset_realloc_dbg
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
apitype: DLLExport
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
caps.latest.revision: 8
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# _aligned_offset_realloc_dbg
Changes the size of a memory block that was allocated with [_aligned_malloc](../VS_visualcpp/_aligned_malloc.md) or [_aligned_offset_malloc](../VS_visualcpp/_aligned_offset_malloc.md) (debug version only).  
  
## Syntax  
  
```  
void * _aligned_offset_realloc_dbg(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Parameters  
 [in] `memblock`  
 The current memory block pointer.  
  
 [in] `size`  
 The size of the memory allocation.  
  
 [in] `alignment`  
 The alignment value, which must be an integer power of 2.  
  
 [in] `offset`  
 The offset into the memory allocation to force the alignment.  
  
 [in] `filename`  
 Pointer to the name of the source file that requested the `aligned_offset_realloc` operation or NULL.  
  
 [in] `linenumber`  
 Line number in the source file where the `aligned_offset_realloc` operation was requested or NULL.  
  
## Return Value  
 `_aligned_offset_realloc_dbg` returns a void pointer to the reallocated (and possibly moved) memory block. The return value is `NULL` if the size is zero and the buffer argument is not `NULL`, or if there is not enough available memory to expand the block to the given size. In the first case, the original block is freed. In the second case, the original block is unchanged. The return value points to a storage space that is guaranteed to be suitably aligned for storage of any type of object. To get a pointer to a type other than void, use a type cast on the return value.  
  
## Remarks  
 `_aligned_offset_realloc_dbg` is a debug version of the [_aligned_offset_realloc](../VS_visualcpp/_aligned_offset_realloc.md) function. When [_DEBUG](../VS_visualcpp/_DEBUG.md) is not defined, each call to `_aligned_offset_realloc_dbg` is reduced to a call to _`aligned_offset_realloc`. Both \_`aligned_offset_realloc` and `_aligned_offset_realloc_dbg` reallocate a memory block in the base heap, but `_aligned_offset_realloc_dbg` accommodates several debugging features: buffers on either side of the user portion of the block to test for leaks, a block type parameter to track specific allocation types, and `filename`/`linenumber` information to determine the origin of allocation requests.  
  
 Like [_aligned_offset_malloc](../VS_visualcpp/_aligned_offset_malloc.md), `_aligned_offset_realloc_dbg` allows a structure to be aligned at an offset within the structure.  
  
 `_realloc_dbg` reallocates the specified memory block with slightly more space than the requested `newSize`. `newSize` might be greater or less than the size of the originally allocated memory block. The additional space is used by the debug heap manager to link the debug memory blocks and to provide the application with debug header information and overwrite buffers. The reallocation might result in moving the original memory block to a different location in the heap, as well as changing the size of the memory block. If the memory block is moved, the contents of the original block are overwritten.  
  
 This function sets `errno` to `ENOMEM` if the memory allocation failed or if the requested size was greater than `_HEAP_MAXREQ`. For more information about `errno`, see [errno, _doserrno, _sys_errlist, and _sys_nerr](../VS_visualcpp/errno--_doserrno--_sys_errlist--and-_sys_nerr.md). Also, `_aligned_offset_realloc_dbg` validates its parameters. If `alignment` is not a power of 2 or if `offset` is greater than or equal to `size` and nonzero, this function invokes the invalid parameter handler, as described in [Parameter Validation](../VS_visualcpp/Parameter-Validation.md). If execution is allowed to continue, this function returns `NULL` and sets `errno` to `EINVAL`.  
  
 For information about how memory blocks are allocated, initialized, and managed in the debug version of the base heap, see [CRT Debug Heap Details](../Topic/CRT%20Debug%20Heap%20Details.md). For information about the allocation block types and how they are used, see [Types of blocks on the debug heap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap). For information about the differences between calling a standard heap function and its debug version in a debug build of an application, see [Debug Versions of Heap Allocation Functions](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_aligned_offset_realloc_dbg`|<crtdbg.h>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## Libraries  
 Debug versions of [C run-time libraries](../VS_visualcpp/CRT-Library-Features.md) only.  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## See Also  
 [Debug Routines](../VS_visualcpp/Debug-Routines.md)