# JavaScript
//实现json对象数组的排序
<div id="tbllayout">
	<table class="gridtable" id="ia" border="1">
		<tr>
			<th>员工工号</th>
			<th>员工姓名</th>
			<th>员工年龄</th>
		</tr>
	</table>
	<table class="gridtable" id="ib" border="1">
		<tr>
			<th>员工工号[排序]</th>
			<th>员工姓名</th>
			<th>员工年龄</th>
		</tr>
	</table>
	<table class="gridtable" id="ic" border="1">
		<tr>
			<th>员工工号[排序]</th>
			<th>员工姓名</th>
			<th>员工年龄[排序]</th>
		</tr>
	</table>
</div>
<script type="text/javascript">
$(function(){
	var peoples=[
		{'card_id':"p001",'p_name':'Linda','p_age':18},
		{'card_id':"p005",'p_name':'Tom','p_age':20},
		{'card_id':"p003",'p_name':'Mary','p_age':19},
		{'card_id':"p002",'p_name':'Bob','p_age':26},
		{'card_id':"p004",'p_name':'Lucy','p_age':17},
	];
	$.each(peoples,function(index,value){
		$("#ia").append('<tr><td>'+value.card_id+'</td><td>'+value.p_name+'</td><td>'+value.p_age+'</td></tr>');
	})
	var card_id_peoples=peoples.sort(function(a,b){
		if(a.card_id<b.card_id) return -1;
		if(a.card_id>b.card_id) return 1;
		return 0;
	})
	$.each(card_id_peoples,function(index,value){
		$("#ib").append('<tr><td>'+value.card_id+'</td><td>'+value.p_name+'</td><td>'+value.p_age+'</td></tr>');
	})
	var p_age_peoples=peoples.sort(function(a,b){
		return (a.p_age-b.p_age);
	})
	$.each(p_age_peoples,function(index,value){
		$("#ic").append('<tr><td>'+value.card_id+'</td><td>'+value.p_name+'</td><td>'+value.p_age+'</td></tr>');
	})
})
</script>


