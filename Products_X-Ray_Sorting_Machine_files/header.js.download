if (screen.width > 1024) {
	$(document).ready(function(){
		var windowScrollTop = $(window).scrollTop();
		if(windowScrollTop>=200){
			$("header").addClass("TopHeader");
		}else{
			$("header").removeClass("TopHeader");
		};
		$(window).scroll(function(){
			var windowScrollTop = $(window).scrollTop();
			if(windowScrollTop>=200){
				$("header").addClass("TopHeader");
			}else{
				$("header").removeClass("TopHeader");
			};
		});
	});
};



// var w = $(window).width();
if (screen.width < 1025) {
	$(".nav_menu").click(function () {
		//        event.stopPropagation();
		$(this).toggleClass("on");
		$(".i_nav").stop().slideToggle();
	});
	$('.i_nav>li').each(function() {
		if($(this).find("ul").has('li').length>0){
			$(this).append("<span></span>");
		};

	});
	$('.i_nav>li').each(function() {
		$(this).find("span").click(function () {
			$(this).parent().find("ul").slideToggle(300);
			if($(this).hasClass("on")){
				$(this).removeClass("on") ;
			}else{
				$(this).addClass("on") ;
			}
		});
	});
};





if (screen.width > 1024) {
	$(document).ready(function () {
		var windowScrollTop = $(window).scrollTop();
		if (windowScrollTop >= 1100) {
			$(".cates333").addClass("highlight");
		} else {
			$(".cates333").removeClass("highlight");
		};
		$(window).scroll(function () {
			var windowScrollTop = $(window).scrollTop();
			if (windowScrollTop >= 1100) {
				$(".cates333").addClass("highlight");
			} else {
				$(".cates333").removeClass("highlight");
			};
		});
	});
};





// pc端 导航下拉 默认下拉菜单
if(screen.width > 1024){
	$('.i_nav .menu-item-has-children').hover(function() {
		$(this).find('.sub-menu').stop().slideToggle(300);
	});
};

// pc端 导航下拉 产品下拉菜单
if (screen.width > 1024) {
	function handleNavHover(navClass, dropdownClass) {
		var timeout;
		$(navClass).on('mouseenter', function () {
			clearTimeout(timeout);
			$(this).addClass('active');
			$(dropdownClass).stop().slideDown(300);
		}).on('mouseleave', function () {
			var navElement = $(this);
			clearTimeout(timeout);
			timeout = setTimeout(function() {
				navElement.removeClass('active');
				$(dropdownClass).stop().slideUp(300);
			}, 0);
		});

		$(document).on('mouseenter', dropdownClass, function () {
			clearTimeout(timeout);
			$(dropdownClass).stop().slideDown(300);
		}).on('mouseleave', dropdownClass, function () {
			var navElement = $(navClass);
			clearTimeout(timeout);
			timeout = setTimeout(function() {
				navElement.removeClass('active');
				$(dropdownClass).stop().slideUp(300);
			}, 0);
		});
	}

	handleNavHover('.nav_dropdown_menu1', '.nav_dropdown_item1');
	handleNavHover('.nav_dropdown_menu2', '.nav_dropdown_item2');
	handleNavHover('.nav_dropdown_menu3', '.nav_dropdown_item3');
	handleNavHover('.nav_dropdown_menu4', '.nav_dropdown_item4');
	handleNavHover('.nav_dropdown_menu5', '.nav_dropdown_item5');
}


// 语言




// 搜索 + 语言
$(document).ready(function(){
	$(".top_search_ico").click(function(){
		$(this).toggleClass("on")
		$(".top_search").toggleClass("on");
	});
	$(".language .language_icon").click(function(){
		$(this).toggleClass("on");
		$(".language_list").toggleClass("on");
	});
	$(document).click(function(event){
		if(!$(event.target).closest('.top_search_ico, .top_search').length){
			$(".top_search_ico").removeClass("on");
			$(".top_search").removeClass("on");
		}
		if(!$(event.target).closest('.language .language_icon, .language_list').length){
			$(".language .language_icon").removeClass("on");
			$(".language_list").removeClass("on");
		}
	});
});




/**********************************

* tabso
* Copyright (c) yeso!
* Date: 2010-07-28

璇存槑锛�
* 搴旂敤瀵硅薄蹇呴』涓鸿垖绛炬寜閽殑鐩存帴鐖跺厓绱狅紝涓旂埗鍏冪礌鍐呬笉鍖呭惈鍏朵粬闈炴寜閽厓绱�
* example: $( ".menus_wrap" ).tabso({ cntSelect:".content_wrap",tabEvent:"mouseover" });
* cntSelect:鍐呭鍧楃殑鐩存帴鐖跺厓绱犵殑 jq 閫夋嫨鍣�
* tabEvent:瑙﹀彂浜嬩欢鍚�
* tabStyle:鍒囨崲鏂瑰紡銆傚彲鍙栧€硷細"normal" "fade" "move" "move-fade" "move-animate"
* direction:绉诲姩鏂瑰悜銆傚彲鍙栧€硷細"left" "top" 锛坱abStyle涓�"move"鎴�"move-fade" "move-animate"鏃舵湁鏁堬級
* aniMethod:鍔ㄧ敾鏂规硶锛堢壒娈婃晥鏋滈渶鎻掍欢锛堝锛歟asing锛夋敮鎸侊紝tabStyle涓�"move-animate"鏃舵湁鏁堬級
* aniSpeed:鍔ㄧ敾閫熷害
* onStyle:鑿滃崟閫変腑鏍峰紡鍚�
**********************************/

; (function ($) {

	$.fn.tabso = function (options) {

		var opts = $.extend({}, $.fn.tabso.defaults, options);

		return this.each(function (i) {
			var _this = $(this);
			var $menus = _this.children(opts.menuChildSel);
			var $container = $(opts.cntSelect).eq(i);

			if (!$container) return;

			if (opts.tabStyle == "move" || opts.tabStyle == "move-fade" || opts.tabStyle == "move-animate") {
				var step = 0;
				if (opts.direction == "left") {
					step = $container.children().children(opts.cntChildSel).outerWidth(true);
				} else {
					step = $container.children().children(opts.cntChildSel).outerHeight(true);
				}
			}

			if (opts.tabStyle == "move-animate") { var animateArgu = new Object(); }

			$menus[opts.tabEvent](function () {
				var index = $menus.index($(this));
				$(this).addClass(opts.onStyle)
					.siblings().removeClass(opts.onStyle);
				switch (opts.tabStyle) {
					case "fade":
						if (!($container.children(opts.cntChildSel).eq(index).is(":animated"))) {
							$container.children(opts.cntChildSel).eq(index).siblings().css("display", "none")
								.end().stop(true, true).fadeIn(opts.aniSpeed);
						}
						break;
					case "move":
						$container.children(opts.cntChildSel).css(opts.direction, -step * index + "px");
						break;
					case "move-fade":
						if ($container.children(opts.cntChildSel).css(opts.direction) == -step * index + "px") break;
						$container.children(opts.cntChildSel).stop(true).css("opacity", 0).css(opts.direction, -step * index + "px").animate({ "opacity": 1 }, opts.aniSpeed);
						break;
					case "move-animate":
						animateArgu[opts.direction] = -step * index + "px";
						$container.children(opts.cntChildSel).stop(true).animate(animateArgu, opts.aniSpeed, opts.aniMethod);
						break;
					default:
						$container.children(opts.cntChildSel).eq(index).css({ "display": "block" })
							.siblings().css({ "display": "none" });
				}

			});

			$menus.eq(0)[opts.tabEvent]();

		});
	};

	$.fn.tabso.defaults = {
		cntSelect: ".content_wrap",
		tabEvent: "mouseover",
		tabStyle: "normal",
		direction: "top",
		aniMethod: "swing",
		aniSpeed: "fast",
		onStyle: "current",
		menuChildSel: "*",
		cntChildSel: "*"
	};

})(jQuery);
