$(document).ready(function(){
	/*header의 nav 부분 제어*/
	//.nav에 자식들 중에 li선택
	$('.nav>li').mouseover(function(){
		//mouse가 올라갈 경우 이벤트 발생

		//현재 위치의 자식의 submenu를 0.5초로 슬라이드로 내림, 기존에 일어나고 있는 것 멈추기 위해 stop()
		$(this).children('.submenu').stop().slideDown(500);	
	});
	$('.nav>li').mouseleave(function(){
		//mouse가 올라갈 경우 이벤트 발생
		$(this).children('.submenu').stop().slideUp(500);	//현재 위치의 자식의 submenu를 0.5초로 슬라이드로 내림
		
	});



	/*이미지 슬라이드 부분 제어*/
	// 도트 이미지 클릭 시 해당 이미지로 변경
	$('#imgsbar a').click(function(){
		$('#imgsbar a').removeClass('active');		// active라는 클라스를 전부 삭제
		$(this).addClass('active');					// 클릭한 것에 class 추가

		//*****
		var imgLeft = $(this).attr('img-left');		//속성중에 img-left 속성을 가져온다.
		//imgLeft 값은 이미지 위치로 설정된 0, -1000, -2000, -3000, -4000 이 나온다.
		$('#imgs').animate({left: imgLeft}, 1000);

		/*
			이미지의 크기가 1000에 400이었음, 5개를 붙인다고 하면 5000에 400이 됨
			한개의 이미지가 0에서 시작
			다음 그림을 보고 싶으면 그림을 왼쪽으로 1000 shift 하면 되기 때문에 -1000을 한다.
		*/
	});


	/*모달 제어 */
	$('.partner_info img').click(function(){
		$('.modal').show();
	});

	$('.modal button').click(function(){
		$('.modal').hide();
	});	

});

// javascript 부분

/*header에 contact 부분*/
function winOpen(){
	window.open('contact.html', 'child', 'width=500, height=300');	// px 생략 가능
}