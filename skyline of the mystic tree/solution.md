## CPP

### SOLUTION

vector<int> topView(Node* root) {
    vector<int> ans;
    if (!root) return ans;
    map<int,int> mp;
    queue<pair<Node*,int>> q;
    q.push({root,0});
    while (!q.empty()) {
        auto [node,hd] = q.front(); q.pop();
        if (mp.find(hd)==mp.end()) mp[hd]=node->data;
        if (node->left) q.push({node->left,hd-1});
        if (node->right) q.push({node->right,hd+1});
    }
    for (auto &p:mp) ans.push_back(p.second);
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

public static List<Integer> topView(Node root){
    List<Integer> res=new ArrayList<>();
    if(root==null) return res;
    Map<Integer,Integer> map=new TreeMap<>();
    Queue<Pair> q=new LinkedList<>();
    q.add(new Pair(root,0));
    while(!q.isEmpty()){
        Pair p=q.poll();
        if(!map.containsKey(p.hd)) map.put(p.hd,p.node.data);
        if(p.node.left!=null) q.add(new Pair(p.node.left,p.hd-1));
        if(p.node.right!=null) q.add(new Pair(p.node.right,p.hd+1));
    }
    res.addAll(map.values());
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

int* topView(struct Node* root, int *size){
    f=r=0;
    memset(seen,0,sizeof(seen));
    q2[r++] = (struct Pair){root,0};
    int minHd=2005, maxHd=-2005;
    
    while(f<r){
        struct Pair p=q2[f++];
        if(!seen[p.hd+OFFSET]){
            seen[p.hd+OFFSET]=1; 
            val[p.hd+OFFSET]=p.node->data;
            if(p.hd<minHd) minHd=p.hd;
            if(p.hd>maxHd) maxHd=p.hd;
        }
        if(p.node->left) q2[r++] = (struct Pair){p.node->left,p.hd-1};
        if(p.node->right) q2[r++] = (struct Pair){p.node->right,p.hd+1};
    }

    *size = maxHd-minHd+1;
    int *res = malloc((*size)*sizeof(int));
    int idx=0;
    for(int hd=minHd; hd<=maxHd; hd++){
        if(seen[hd+OFFSET]) res[idx++] = val[hd+OFFSET];
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function topView(root){
    if(!root) return [];
    let map=new Map();
    let q=[[root,0]];
    while(q.length){
        let [node,hd]=q.shift();
        if(!map.has(hd)) map.set(hd,node.data);
        if(node.left) q.push([node.left,hd-1]);
        if(node.right) q.push([node.right,hd+1]);
    }
    return [...map.entries()].sort((a,b)=>a[0]-b[0]).map(x=>x[1]);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def topView(root):
    if not root: return []
    q = deque([(root,0)])
    hd_map = {}
    while q:
        node,hd = q.popleft()
        if hd not in hd_map:
            hd_map[hd] = node.data
        if node.left: q.append((node.left,hd-1))
        if node.right: q.append((node.right,hd+1))
    return [hd_map[k] for k in sorted(hd_map.keys())]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256