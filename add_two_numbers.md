# 2. Add Two Numbers

[Leetcode](https://leetcode.com/problems/add-two-numbers/)

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {

        ListNode* head = new ListNode(0);
        ListNode* current = head;
        int res = 0;

        while (l1 != nullptr || l2 != nullptr) {

            int x = (l1 != nullptr) ? l1->val : 0;
            int y = (l2 != nullptr) ? l2->val : 0;
            int sum = x + y + res;

            // fix a
            res = sum / 10;

            current->next = new ListNode(sum % 10);

            current = current->next;
            if (l1 != nullptr) l1 = l1->next;
            if (l2 != nullptr) l2 = l2->next;

        }

        // fix b
        if (res > 0)
            current->next = new ListNode(res);

        return head->next;

    }
};
```