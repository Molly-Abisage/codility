# codility
My solutions to codility.com problems

Equillibrium index (Got 58%) https://codility.com/demo/results/demoU43H7Y-2Z4/
```java
class Solution {
    
    public int solution(int[] A) {
        
        
        int right = 0;
        int left = 0;
        
        for (int i = 0;i < A.length; i ++) {
            right += A[i];
        }
        for (int i = 0; i < A.length; i ++) {
            
            right -= A[i];
            
            if (i == 0) {
                left += 0;
            } else if (i == A.length -1) {
                
                if (left == 0) {
                    return i;
                }
            } else {
                left += A[i -1];
            }
            
            if (left == right) {
                return i;
            }
        }
        return -1;
    }
}
```
TapeEqullibrium (83%) https://codility.com/demo/results/trainingPNNFJ4-B3Y/
```java
import java.util.*;
class Solution {
    
    public int solution(int[] A) {
        
        int right = 0;
        int left = 0;
        int[] num = new int[A.length];
        
        for (int i = 0; i < A.length; i ++) {
            right += A[i];
        }
        for (int i = 0; i < A.length; i ++) {
            right -= A[i];
            left += A[i];
            num[i] = Math.abs(right - left);
        }
        Arrays.sort(num);
        return num[0];
    }
}
```
MissingInteger

Find the minimal positive integer not occurring in a given sequence.
https://codility.com/demo/results/training25FBE5-M36/ Passed with 44%

```java
import java.util.*;

class Solution {
    public int solution(int[] A) {
        Arrays.sort(A);
        if (A.length == 1) {
            return 2;
        }
        List<Integer> ints = new ArrayList<>();
        for (int i = 0; i < A.length; i ++) {
            ints.add(A[i]);
        }
        if (ints.get(0) > 1) {
            return 1;
        }
        for (int i = 1; i < ints.size(); i ++) {
            if (ints.get(i) - ints.get(i - 1) > 1) {
                return (ints.get(i) + ints.get(i - 1)) / 2;
            }
        }
        return ints.get(ints.size() - 1) + 1;
    }
}
```
PermCheck


Check whether array A is a permutation (100%). https://codility.com/demo/results/trainingNGSJA5-DCD/

```java
import java.util.*;
class Solution {
    public int solution(int[] A) {
        
        Hashtable<Integer, Boolean> table = new Hashtable<>();
        
        for (int i = 0; i < A.length; i ++) {
           
            if (table.containsKey(A[i]) || A[i] > A.length) {
                return 0; // is not a perm since A[i] exists more than once
            } else {
                table.put(A[i], true);
            }
        }
        return 1;
    }
}
```
MissingInteger (100% score)
Find the minimal positive integer not occurring in a given sequence.
```java
public class Solution {
    public int solution(int[] A) {
        int positiveCount = 0;        
        for(int i=0; i< A.length; i++) {
            positiveCount++;
        }
        
        int[] B = new int[positiveCount];
        
        for(int i=0; i<A.length; i++) {
            if(A[i]<=A.length && A[i]>0) {
                B[A[i]-1]=1;
            }
        }
        
        int min = B.length+1;
        
        for(int i=0; i<B.length; i++) {
            if(B[i]==0) {
                // min = B[i]+1;
                min = i+1;
                break;
            }
        }
        
        return min;
    }
}
```
CountDiv: Compute number of integers divisible by k in range [a..b]. (50% score)
https://codility.com/demo/results/trainingF4QJ7X-DDW/

```java
class Solution {
    public int solution(int A, int B, int K) {
        return (B/K) - ((A - 1)/K);
    }
}
```
