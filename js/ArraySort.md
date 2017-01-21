###js数组排序和数组去重

+ js数组排序和数组去重
    ```javascript
    //冒泡排序
    function bubbleSort(arr){
        for(var r=1; r<arr.length;r++){
            for(var i=0;i<arr.length-r;i++){
                
                if(arr[i]>arr[i+1]){
                    var temp = arr[i];
                    arr[i]=arr[i+1];
                    arr[i+1]= temp;
                }
            }
        }
        return arr;
    }
    var arr1 = [2,4,3,1,5];
    var res1 = bubbleSort(arr1);
    //插入排序
    function insertSort(arr){
        for (var i=0;i<arr.length;i++){
            var t = arr[i];
            var p = i-1;
            while(t<arr[p]&&p>=0){
                arr[p+1]=arr[p];
                p--;
            }
            arr[p+1]=t;
        }
        return arr;
    }
    var arr2 = [2,4,3,1,9,0,10,0,4,5];
    var res2 = insertSort(arr2);
    //快速排序法
    function quickSort(arr){
        if(arr.length<=1){
            return arr;
        }else{
            var c = arr.splice(Math.floor(arr.lenth/2),1)[0];
            var left=[];
            var right=[];
            for(var i=0; i<arr.length;i++){
                if(arr[i]>c){
                    right.push(arr[i]);
                }else{
                    left.push(arr[i]);
                }
            }
            return quickSort(left).concat(c,quickSort(right));
        }
    }
    var arr3 = [2,4,3,5,5,2,1,0,12,6];
    var res3 =  quickSort(arr3);
        ```
 + js数组去重

    ```javascript
    //js数组去除重复数据1
    
    function arrNotRepeat(arr){
        var newArr = [];
        for(var i=0;i<arr.length;i++){
            if(newArr.indexOf(arr[i])==-1){
                newArr.push(arr[i]);
            }
        }
        return newArr;
    }
    var arrRepeat1 =[1,2,5,4,4,6,3,2,4,0];
    var res4 = arrNotRepeat(arrRepeat1);
    
    
    //js数组去除重复数据2
    function arrUnique(arr){
        var result = [],isRepeated;
        for(var i=0;i<arr.length;i++){
            isRepeated = false;
            for(var j=0;j<result.length;j++){
                if(arr[i]==result[j]){
                    isRepeated =true;
                    break;
                }
            }
            if(!isRepeated){
                result.push(arr[i]);
            }
        }
        return result;
    }
    var arrRepeat2 = [1,4,2,4,5,3,1,2,4,0];
    var res5 = arrUnique(arrRepeat2);
    ```
    
