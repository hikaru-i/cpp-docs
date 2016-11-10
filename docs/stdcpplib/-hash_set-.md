---
title: "&lt;hash_set&gt;"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set header"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 21
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# &lt;hash_set&gt;
> [!NOTE]
>  This header is obsolete. The alternative is [<unordered_set>](../stdcpplib/-unordered_set-.md).  
  
 Defines the container template classes hash_set and hash_multiset and their supporting templates.  
  
## Syntax  
  
```  
#include <hash_set>  
  
```  
  
## Remarks  
  
### Operators  
  
|Hash_set version|Hash_multiset version|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../stdcpplib/-hash_set--operators.md#operator_neq)|[operator!= (hash_multiset)](../stdcpplib/-hash_set--operators.md#operator_neq__hash_multiset_)|Tests if the hash_set or hash_multiset object on the left side of the operator is not equal to the hash_set or hash_multiset object on the right side.|  
|[operator== (hash_set)](assetId:///791b95bd-f917-4716-aea6-add50badbfac)|[operator== (hash_multiset)](assetId:///cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|Tests if the hash_set or hash_multiset object on the left side of the operator is equal to the hash_set or hash_multiset object on the right side.|  
  
### Specialized Template Functions  
  
|Hash_set version|Hash_multiset version|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../stdcpplib/-hash_set--functions.md#swap)|[swap (hash_multiset)](../stdcpplib/-hash_set--functions.md#swap__hash_multiset_)|Exchanges the elements of two hash_sets or hash_multisets.|  
  
### Classes  
  
|||  
|-|-|  
|[hash_compare Class](../stdcpplib/hash_compare-class.md)|Describes an object that can be used by any of the hash associative containers — hash_map, hash_multimap, hash_set, or hash_multiset — as a default **Traits** parameter object to order and hash the elements they contain.|  
|[hash_set Class](../stdcpplib/hash_set-class.md)|Used for the storage and fast retrieval of data from a collection in which the values of the elements contained are unique and serve as the key values.|  
|[hash_multiset Class](../stdcpplib/hash_multiset-class.md)|Used for the storage and fast retrieval of data from a collection in which the values of the elements contained are unique and serve as the key values.|  
  
## See Also  
 [Header Files Reference](../stdcpplib/c---standard-library-header-files.md)   
 [Thread Safety in the C++ Standard Library](../stdcpplib/thread-safety-in-the-c---standard-library.md)   
 [Standard Template Library](../notintoc/standard-template-library.md)
