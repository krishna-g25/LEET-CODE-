class Solution {
private:
    pair<int, int> expandAroundCenter(string& s, int left, int right) {
        while (left >= 0 && right < s.length() && s[left] == s[right]) {
            left--;
            right++;
        }
        return {left + 1, right - 1};
    }
    
public:
    string longestPalindrome(string s) {
        if (s.length() < 2) return s;
        
        int maxStart = 0, maxEnd = 0;
        
        for (int i = 0; i < s.length(); i++) {
            auto [left1, right1] = expandAroundCenter(s, i, i);
            if (right1 - left1 > maxEnd - maxStart) {
                maxStart = left1;
                maxEnd = right1;
            }
            
            if (i < s.length() - 1) {
                auto [left2, right2] = expandAroundCenter(s, i, i + 1);
                if (right2 - left2 > maxEnd - maxStart) {
                    maxStart = left2;
                    maxEnd = right2;
                }
            }
        }
        
        return s.substr(maxStart, maxEnd - maxStart + 1);
    }
};
