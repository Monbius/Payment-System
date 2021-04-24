<script type="text/javascript">

       //调用微信JS api 支付
       function jsApiCall()
       {
           WeixinJSBridge.invoke(
               'getBrandWCPayRequest',
               {$pay_online},
               function(res){
                   WeixinJSBridge.log(res.err_msg);
                   if(res.err_msg == "get_brand_wcpay_request:ok"){
                   //alert(res.err_code+res.err_desc+res.err_msg);
                       window.location.href="http://blog.sina.com.cn/u/1863605217";
                   }else{
                       //返回跳转到订单详情页面
                       alert(支付失败);
                       window.location.href="http://blog.sina.com.cn/u/1863605217";
                         
                   }
               }
           );
       }

       function callpay()
       {
           if (typeof WeixinJSBridge == "undefined"){
               if( document.addEventListener ){
                   document.addEventListener('WeixinJSBridgeReady', jsApiCall, false);
               }else if (document.attachEvent){
                   document.attachEvent('WeixinJSBridgeReady', jsApiCall);
                   document.attachEvent('onWeixinJSBridgeReady', jsApiCall);
               }
           }else{
               jsApiCall();
           }
       }

   </script>
