# codility
My solutions to codility.com problems

Equillibrium index (Got 58%) https://codility.com/demo/results/demoU43H7Y-2Z4/

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
