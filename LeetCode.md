### 两数之和https://leetcode-cn.com/problems/two-sum/submissions/

#### 方法一
```
//原生对象
var twoSum = function(nums, target) {
    // keys --> { '数字' : 数字下标 }
    var keys = {};
    for(var i = 0, j = nums.length; i < j; i++) {
        var diff = target - nums[i];
        // 判断差值diff在键值对中是否存在 是则找到匹配数字
        if(!isNaN(keys[diff])) {
            return [keys[diff], i];
        }
        // 未出现匹配值 将数字存入键值对中以备后续判断
        keys[nums[i]] = i;
    }
}
```

#### 方法二
```
// Map对象
var twoSum = function(nums, target) {
    // keys --> { '数字' : 数字下标 }
    var keys = new Map();
    for(var i = 0, j = nums.length; i < j; i++) {
        var diff = target - nums[i];
        // 判断差值diff在键值对中是否存在 是则找到匹配数字
        if(keys.has(diff)) {
            return [keys.get(diff), i];
        }
        // 未出现匹配值 将数字存入键值对中以备后续判断
        keys.set(nums[i], i);
    }
}
```
