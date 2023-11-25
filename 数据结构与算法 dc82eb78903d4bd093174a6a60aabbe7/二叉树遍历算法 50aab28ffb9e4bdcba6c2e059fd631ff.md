---
layout: default
---
# 二叉树遍历算法

前序遍历

```cpp
void PreOrder(BinTreeNode<T> *BT) {
        if (BT) {
            cout << BT->data << " ";
            PreOrder(BT->leftChild);
            PreOrder(BT->rightChild);
        }
    }
```

中序遍历

```cpp
void InOrder(BinTreeNode<T> *BT) {
        if (BT) {
            InOrder(BT->leftChild);
            cout << BT->data << " ";
            InOrder(BT->rightChild);
        }
    }
```

后序遍历

```cpp
void PostOrder(BinTreeNode<T> *BT) {
        if (BT) {
            PostOrder(BT->leftChild);
            PostOrder(BT->rightChild);
            cout << BT->data << " ";
        }
    }
```

层序遍历

```cpp
void LevelOrder(BinTreeNode<T> *root) {
        queue<BinTreeNode<T> *> Q;   //开队列
				BinTreeNOde<T> *BT;
        Q.push(root);   //将根节点压入队列，后面用队列空，作为树结束的标志
        while (!Q.empty()) {
            BT = Q.front(); //按照根-左-右一层层弹出输出
            Q.pop();
            cout << BT->data << " ";
            if (BT->leftChild != nullptr) {
                Q.push(BT->leftChild);
            }
            if (BT->rightChild != nullptr) {
                Q.push(BT->rightChild);
            }
        }
        cout << endl;
    }
```

前序非递归

```cpp
void PreOrder_NoRecurve() {
        cout << "先序非递归遍历：" << endl;
        stack<BinTreeNode<T> *> s;
        BinTreeNode<T> *BT;
        BT = root;
        if (s.empty()) {
            s.push(nullptr);//这样做的好处是，到最后BT会变成栈底的nullptr，循环只需要一个条件，并且防止越界。如果检查栈是否为空，则一开始栈是空的，很麻烦。
        }
        while (BT) {
            cout << BT->data << ' ';
            if (BT->rightChild) {
                s.push(BT->rightChild);
            }
            if (BT->leftChild) {
                BT = BT->leftChild;
            } else {
                BT = s.top();
                s.pop();
            }
        }
        cout << endl;

    }
```

中序非递归

```cpp
void InOrder_NoRecurve() {
        cout << "中序非递归遍历：" << endl;
        stack<BinTreeNode<T> *> s;
        BinTreeNode<T> *BT;
        BT = root;
        do {
            while (BT) {
                s.push(BT);
                BT = BT->leftChild;
            }
            if (!s.empty())
            {
                BT = s.top();
                cout << BT->data << ' ';
                s.pop();
                BT = BT->rightChild;
            }

        } while (!s.empty() || BT);
        cout << endl;
    }
```

后续非递归

```cpp
void PostOrder_NoRecurve() {
        cout << "后序非递归遍历：" << endl;
        stack<BinTreeNode<T> *> s;
        s.push(root);   //先把根放入栈中，方便后面用栈空来判定结束，因为根一定最后一个弹出
        BinTreeNode<T> *lastPop = nullptr;
        do {
            while (s.top()->leftChild != nullptr)    //遍历到最左节点
            {
                s.push(s.top()->leftChild);
            }
            while (!s.empty())   //这个循环的作用是将所有的右分枝遍历完，弹栈至最前面节点，如右斜树
            {
                if (lastPop == s.top()->rightChild || s.top()->rightChild == nullptr)
                    //当前节点左右子树都遍历完｜｜为右叶子节点，即右子树遍历完成
                {
                    cout << s.top()->data << ' ';   //输出弹出当前栈顶数据并lastPop暂存
                    lastPop = s.top();
                    s.pop();
                } else if (s.top()->rightChild != nullptr) //右子树不为空，进入右子树
                {
                    s.push(s.top()->rightChild);
                    break;  //进入右子树后开始遍历右子树中的左子树
                }
            }
        } while (!s.empty());
        cout << endl;
    }
```

二叉树宽度

```cpp
void TreeWidth() {
        queue<BinTreeNode<T> *> Q;
        BinTreeNode<T> *BT;
        Q.push(root);
        int maxwidth = 1;
        int popped = 0;
        while (!Q.empty()) {
            BT = Q.front();
            if (BT->leftChild) {
                Q.push(BT->leftChild);
            }
            if (BT->rightChild) {
                Q.push(BT->rightChild);
            }
            Q.pop();
            popped++;
            if (popped == maxwidth) {
                popped = 0;
                if (Q.size() > maxwidth)maxwidth = Q.size();
            }

        }
        cout << "宽度为：" << maxwidth << endl;
    }
```