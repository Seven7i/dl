<!DOCTYPE html><!--H5标准声明，使用 HTML5 doctype，不区分大小写-->
 
<head lang="en">
    <!--标准的 lang 属性写法-->
 
    <meta charset='utf-8'>
    <!-- 声明文档使用的字符编码-->
 
    <div>
        <input type="text" id="Tex"><button> 解密</button><button>加密</button><br />
        <div rows="10" cols="40">
            <span id="Texr"></span>
        </div>
    </div>
    <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
        <script type="text/javascript" src="http://tool.oschina.net/js/CryptoJS/components/core-min.js"></script>
        <script type="text/javascript" src="http://tool.oschina.net/js/CryptoJS/components/enc-base64-min.js"></script>
        <script src="http://tool.oschina.net/js/CryptoJS/components/enc-base64-min.js"></script>
    <script>
        var Table = {
            '乾': 'A',
            '坤': 'B',
            '屯': 'C',
            '蒙': 'D',
            '需': 'E',
            '讼': 'F',
            '师': 'G',
            '比': 'H',
            '小畜': 'I',
            '履': 'J',
            '泰': 'K',
            '否': 'L',
            '同人': 'M',
            '大有': 'N',
            '谦': 'O',
            '豫': 'P',
            '随': 'Q',
            '蛊': 'R',
            '临': 'S',
            '观': 'T',
            '噬嗑': 'U',
            '贲': 'V',
            '剥': 'W',
            '复': 'X',
            '无妄': 'Y',
            '大畜': 'Z',
            '颐': 'a',
            '大过': 'b',
            '坎': 'c',
            '离': 'd',
            '咸': 'e',
            '恒': 'f',
            '遁': 'g',
            '大壮': 'h',
            '晋': 'i',
            '明夷': 'j',
            '家人': 'k',
            '睽': 'l',
            '蹇': 'm',
            '解': 'n',
            '损': 'o',
            '益': 'p',
            '夬': 'q',
            '姤': 'r',
            '萃': 's',
            '升': 't',
            '困': 'u',
            '井': 'v',
            '革': 'w',
            '鼎': 'x',
            '震': 'y',
            '艮': 'z',
            '渐': '1',
            '归妹': '2',
            '丰': '3',
            '旅': '4',
            '巽': '5',
            '兑': '6',
            '涣': '7',
            '节': '8',
            '中孚': '9',
            '小过': '0',
            '既济': '+',
            '未济': '/'
 
        };
 
        function Jie() {
            var str = $("#Tex").val()
            var ta = "";
            for(var i = 0; i < str.length; i++) {
                $.each(Table, function(n, value) { 
                    str = str.replace(n, value); 
                });
            }
            console.log(str)
            //var sda = base64_decode(str);
                var words  = CryptoJS.enc.Base64.parse(str);
            var sda=words.toString(CryptoJS.enc.Utf8)
            console.log(sda)
            $("#Texr").text(sda.replace(/<\/?[^>]*>/gim, "")); //去掉所有的html标记)
        }
 
        function jia() {
            var str = $("#Tex").val();
            var ta = "";
             
            str = base64_encode();
            console.log(str)
            for(var i = 0; i < str.length; i++) {
                for(var key in Table) {
                    if(Table[key] == str[i]) {
                        ta += key
                    }
                }
            }
 
            $("#Texr").text(ta)
        }
 
function base64_encode(){
    var str=CryptoJS.enc.Utf8.parse($("#Tex").val());
    var base64=CryptoJS.enc.Base64.stringify(str);
    return base64;
}
function base64_decode(){
 
}
 
    </script>
