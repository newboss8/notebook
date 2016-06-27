JS控制输入框只能输出小数点以后两位的金额:
		$(function(){
				$("#amount").on('keyup', function (event) {
			    var $amountInput = $(this);
			    //响应鼠标事件，允许左右方向键移动 
			    event = window.event || event;
			    if (event.keyCode == 37 | event.keyCode == 39) {
			        return;
			    }
			    //先把非数字的都替换掉，除了数字和. 
			    $amountInput.val($amountInput.val().replace(/[^\d.]/g, "").
			        //只允许一个小数点              
			        replace(/^\./g, "").replace(/\.{2,}/g, ".").
			        //只能输入小数点后两位
			        replace(".", "$#$").replace(/\./g, "").replace("$#$", ".").replace(/^(\-)*(\d+)\.(\d\d).*$/, '$1$2.$3'));
			            });
				$("#amount").on('blur', function () {
				    var $amountInput = $(this);
				    //最后一位是小数点的话，移除
				    $amountInput.val(($amountInput.val().replace(/\.$/g, "")));
				});
		})



验证金额参考:
		function clearNoNum(obj){

			obj.value = obj.value.replace(/[^\d.]/g,""); //清除"数字"和"."以外的字符

			obj.value = obj.value.replace(/^\./g,""); //验证第一个字符是数字而不是

			obj.value = obj.value.replace(/\.{2,}/g,"."); //只保留第一个. 清除多余的

			obj.value = obj.value.replace(".","$#$").replace(/\./g,"").replace("$#$",".");

			obj.value = obj.value.replace(/^(\-)*(\d+)\.(\d\d).*$/,'$1$2.$3'); //只能输入两个小数

		}


验证金额参考:
		var price = 11.11;
		checkPrice(price );
		function checkPrice(price){
		  return (/^(([1-9]\d*)|\d)(\.\d{1,2})?$/).test(price.toString());
		}



遍历二维JSON对象:
		$.each(data, function(index, val) {
			if ($.type(val)=='object') {
				$.each(val, function(index, val) {
					var str = '<h1>'+index+':'+'</h1>';
					var str1 = '<span>'+val+'</span>';
					content1.append(str);
					content1.append(str1);
				});
			}else{
				var str = '<h1>'+index+':'+'</h1>';
				var str1 = '<span>'+val+'</span>';
				content.append(str);
				content.append(str1);
			}
		});
