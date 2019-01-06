#### Finding number of times b appears in sorted list:
public class Solution {
    // DO NOT MODIFY THE LIST. IT IS READ ONLY
    public int findCount(final List<Integer> a, int b) {
        int upper = binary_search_index(a, b, false);

        int lower = binary_search_index(a, b, true);
        
        if(lower == -1) return 0;
        
        return upper - lower + 1;
    }
    
    private static int binary_search_index(List<Integer> arr, int x, boolean searchFirst) {
        int n = arr.size();
        int l=0,h=n-1;
        int result = -1;
        while(l<=h) {
            int mid = l + (h-l)/2;

            int k = arr.get(mid);

            if(k == x) {
                result = mid;

                if(searchFirst)
                    h = mid - 1;
                else l = mid + 1;
            }
            else if(k > x) h = mid - 1;
            else l = mid + 1;
        }

        return result;
    }
}

