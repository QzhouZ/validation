# validation
表单验证插件

###使用说明
在表单输入框里加``入data-validtype=""``,	
目前验证规则有：	
不能为空``data-validtype="noEmpty"``,	
邮箱地址``data-validtype="email"``,		
数字``data-validtype="number"``,	
手机号码``data-validtype="mobile"``,	
身份证号码``data-validtype="idCard"``, 
通过``data-msg=""``,可以修改提示内容	

###表单里的html结构

	<form id="form" action="" method="post">
		<div class="form-group">
	        <label>
	            <span class="label">登录账号：</span>
	            <input type="text" data-validtype="account" data-msg="请输入5~10位" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">手机号码：</span>
	            <input type="text" data-validtype="mobile" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">邮箱地址：</span>
	            <input type="text" data-validtype="email" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">身份证号：</span>
	            <input type="text" data-validtype="idCard" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">年龄：</span>
	            <input type="text" data-validtype="number" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">密码：</span>
	            <input type="text" data-validtype="noEmpty" class="J_old" />
	        </label>
	    </div>
	    <div class="form-group">
	        <label>
	            <span class="label">确认密码：</span>
	            <input type="text" data-validtype="same" />
	        </label>
	    </div>
	    <div class="form-group">
	        <span class="label">&nbsp;</span>
	        <button class="btn btn-warning" type="submit" data-msg="保存中...">提交</button>
	    </div>
	</form>

###相关属性说明

	seajs.use("validation", function(validatebox,popup) {
	    validatebox({
	        formId: "#form", // 对应表单ID
	        beforeSubmit: function() {
	        	// 提交前操作
	        }, 
	        ajaxSuccess: function(data) {
	            // 表单提交成功后的回调
	            alert(data.info);
	        }
	    });
	});
    