<script>
function getRandom(ar, maxNum) {
    var arr=[];for(var i=0; i<ar.length; i++){ arr[i]=ar[i];}
    var numArr = [];
    var arrLength = arr.length;
    for (var i = 0; i < arrLength; i++) {
        var Rand = arr.length;
        //取出随机数 
        var number = Math.floor(Math.random() * arr.length); //生成随机数num
        numArr.push(arr[number]); //往新建的数组里面传入数值
        arr.splice(number, 1); //传入一个删除一个，避免重复
        if (arr.length <= arrLength - maxNum) {
            return numArr;
        }
    }
}
namelist=["陈泓月","陈秭赟","崔佳一","丁春霖","傅浩宸","高鼎然","贺梓喆","胡骁玮","柯燕希","刘美含","刘芮含","刘思然","李昀松","聂浩然","孙伊然","佟冠松","魏楚洵","熊禹坤","于涵博","俞婧怡","赵梦湉","赵子淇","朱育州"];
function getName(){
    var num=document.getElementById("w").value;
    if(isNaN(num) || parseInt(num)>namelist.length ||num=="") {alert("输入无效请重输");return}
    var tmp=getRandom(namelist,parseInt(num))
    document.getElementById("q").innerHTML=tmp
}
</script>
<h1>超级点名器1-4</h1>
<span id="q">未点名</span><br/><br/>
<span id="e">点名人数:</span><input type="text" id="w"/><br/>
<button onclick="getName()">点名</button>
