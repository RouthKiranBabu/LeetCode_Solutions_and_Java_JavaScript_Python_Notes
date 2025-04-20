# ✅ Java Program to Print All ArrayList Methods:
```java
package Package;
import java.util.ArrayList;
import java.lang.reflect.Method;
public class firstClass {
	public static void main(String[] args) {
		Class<?> arrayListClass = ArrayList.class;
        // Get all declared methods
        Method[] methods = arrayListClass.getDeclaredMethods();
        System.out.println("All methods of ArrayList:\n");
        int i = 1;
        for (Method method : methods) {
            System.out.print(i + ". " + method.getName() + ", ");
            i += 1;
            if (i % 10 == 0) System.out.println();
        }
	}
}
```
## Output
```bash
All methods of ArrayList:

1. remove, 2. remove, 3. size, 4. get, 5. equals, 6. hashCode, 7. clone, 8. sort, 9. indexOf, 
10. clear, 11. lastIndexOf, 12. isEmpty, 13. replaceAll, 14. add, 15. add, 16. add, 17. subList, 18. toArray, 19. toArray, 
20. iterator, 21. contains, 22. spliterator, 23. addAll, 24. addAll, 25. set, 26. readObject, 27. writeObject, 28. forEach, 29. ensureCapacity, 
30. trimToSize, 31. elementData, 32. grow, 33. grow, 34. indexOfRange, 35. lastIndexOfRange, 36. rangeCheckForAdd, 37. fastRemove, 38. equalsArrayList, 39. equalsRange, 
40. checkForComodification, 41. hashCodeRange, 42. outOfBoundsMsg, 43. outOfBoundsMsg, 44. shiftTailOverGap, 45. batchRemove, 46. elementAt, 47. removeIf, 48. removeIf, 49. nBits, 
50. setBit, 51. isClear, 52. replaceAllRange, 53. getFirst, 54. getLast, 55. addFirst, 56. addLast, 57. removeFirst, 58. removeLast, 59. removeRange, 
60. removeAll, 61. retainAll, 62. listIterator, 63. listIterator, 64. checkInvariants, 
```

# ✅ Javascript Program to Print All Array Methods:
```javascript
const arrayMethods = Object.getOwnPropertyNames(Array.prototype)
  .filter(prop => typeof Array.prototype[prop] === 'function');
console.log(arrayMethods);
```
## Output
```bash
[
  'constructor',    'at',        'concat',
  'copyWithin',     'fill',      'find',
  'findIndex',      'findLast',  'findLastIndex',
  'lastIndexOf',    'pop',       'push',
  'reverse',        'shift',     'unshift',
  'slice',          'sort',      'splice',
  'includes',       'indexOf',   'join',
  'keys',           'entries',   'values',
  'forEach',        'filter',    'flat',
  'flatMap',        'map',       'every',
  'some',           'reduce',    'reduceRight',
  'toLocaleString', 'toString',  'toReversed',
  'toSorted',       'toSpliced', 'with'
]
```
# ✅ Python Program to Print All Array Methods:
```python
import array
# Create a sample array
arr = array.array('i', [1, 2, 3])
# Print all available methods and attributes
print(dir(arr))
```
# Output
```bash
['__add__', '__buffer__', '__class__', '__class_getitem__', '__contains__', '__copy__', '__deepcopy__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getstate__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__module__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__release_buffer__', '__repr__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'buffer_info', 'byteswap', 'count', 'extend', 'frombytes', 'fromfile', 'fromlist', 'fromunicode', 'index', 'insert', 'itemsize', 'pop', 'remove', 'reverse', 'tobytes', 'tofile', 'tolist', 'tounicode', 'typecode']
```