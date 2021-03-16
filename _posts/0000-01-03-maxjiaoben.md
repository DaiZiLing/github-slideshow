messagebox"现在进行步兵Idel_1序列渲染，请确认步兵已经朝向正北方！\n\n脚本执行过程中可长按ESC停止脚本运行"
	clearSelection()
	select $ShadowPlane
	$.receiveshadows = off
	clearSelection()
	select $centerdummy
			rotate $ (angleaxis -225 [0,0,1])
	render RA2目标摄像机 framerange:#active outputFile:("D:\RA2Scripts\INF8\W01.png") vfb:off
		rotate $ (angleaxis 225 [0,0,1])
		clearSelection()
	select $ShadowPlane
	$.receiveshadows = on
		clearSelection()
		select $ShadowPlane
	actionMan.executeAction 0 "40044"  
	meditMaterials[16] = MatteShadow ()
	$.material = meditMaterials[16]
	$.receiveshadows = off
	clearSelection()
	select $ShadowPlane
	$.receiveshadows = on
	clearSelection()
	select #($基本光照, $基本光照001, $基本光照002)
	$.renderable = off
	clearSelection()
	select $centerdummy
			rotate $ (angleaxis -225 [0,0,1])
	render RA2目标摄像机 framerange:#active outputFile:("D:\RA2Scripts\INF8\SW01.png") vfb:off
		rotate $ (angleaxis 225 [0,0,1])
		clearSelection()
	messagebox" 步兵空闲序列_1渲染完毕！"