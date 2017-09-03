** string & data structure
 - 슬라이스의 복사
1.copy(desc, src)
2.append([]int(nil), src...)

 - 슬라이스 삽입 및 삭제
 1. a = append(a[:i+1], a[i:]...)
 `` if i < len(a) {
      a = append(a[:i+1], a[i]...)
    } else {
      a = append(a,x)
    }
 ``

 - map
 1. m := make(map[keyType]valueType)
 2. m := map[keyType]valueType{}
 3. value, ok := m[key]
 4. 포인터 취하지 않아도 값 변경 가능
 
