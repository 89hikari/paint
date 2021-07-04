<template>
    <div>
        <div>
        <nav>
            <ul id="main-menu">
                <div>
                    <li>Файл</li>
                    <ul class="menu">
                        <a href="#" @click="newCanvas()"><li>Новый</li></a>
                        <a href="#" @click="openFile()"><li>Открыть</li></a>
                        <a href="#" id="save"><li>Сохранить</li></a>
                        <a href="#" @click="window.close()"><li>Закрыть</li></a>
                    </ul>
                </div>
            </ul>
        </nav>
    </div>
    <div id="sidebar">
        <div id="buttons">
            <button title="Eraser/Color Eraser"><i class="fas fa-eraser"></i></button>
            <button title="Fill With Color"><i class="fas fa-fill-drip"></i></button>
            <button title="Pencil"><i class="fas fa-pencil-alt"></i></button>
            <button title="Text"><i class="fas fa-font"></i></button>
            <button title="Line"><i class="fas fa-slash"></i></button>
            <button title="Rectangle"><img class="rect" src="./../assets/rectangle.png" alt=""></button>
            <button title="Ellipse"><i class="far fa-circle"></i></button>
        </div>
        <div id="color-select"></div>
    </div>

    <div id="canvas-container">
        <canvas id="canvas" width="1920" height="1080"></canvas>
        <div id="text-editor">
            <select name="fonts" id="fonts">
                <option value="Arial" selected="selected">Arial</option>
                <option value="Arial Black">Arial Black</option>
                <option value="Arial Narrow">Arial Narrow</option>
                <option value="Calibri">Calibri</option>
                <option value="Cambria">Cambria</option>
                <option value="Cambria Math">Cambria Math</option>
                <option value="Candara">Candara</option>
                <option value="Comic Sans MS">Comic Sans MS</option>
                <option value="Consolas">Consolas</option>
                <option value="Constantia">Constantia</option>
                <option value="Corbel">Corbel</option>
                <option value="Courier">Courier</option>
                <option value="Courier New">Courier New</option>
                <option value="Franklin Gothic Heavy">Franklin Gothic Heavy</option>
                <option value="Franklin Gothic Medium">Franklin Gothic Medium</option>
                <option value="Gabriola">Gabriola</option>
                <option value="Georgia">Georgia</option>
                <option value="Helvetica">Helvetica</option>
                <option value="Impact">Impact</option>
                <option value="Lucida Console">Lucida Console</option>
                <option value="Lucida Sans Unicode">Lucida Sans Unicode</option>
                <option value="MS Gothic">MS Gothic</option>
                <option value="MS PGothic">MS PGothic</option>
                <option value="MS UI Gothic">MS UI Gothic</option>
                <option value="MV Boli">MV Boli</option>
                <option value="Malgun Gothic">Malgun Gothic</option>
                <option value="Microsoft Himalaya">Microsoft Himalaya</option>
                <option value="Microsoft JhengHei">Microsoft JhengHei</option>
                <option value="Microsoft Sans Serif">Microsoft Sans Serif</option>
                <option value="Microsoft YaHei">Microsoft YaHei</option>
                <option value="Microsoft Yi Baiti">Microsoft Yi Baiti</option>
                <option value="MingLiU-ExtB">MingLiU-ExtB</option>
                <option value="MingLiU_HKSCS-ExtB">MingLiU_HKSCS-ExtB</option>
                <option value="Mongolian Baiti">Mongolian Baiti</option>
                <option value="NSimSun">NSimSun</option>
                <option value="PMingLiU-ExtB">PMingLiU-ExtB</option>
                <option value="Palatino Linotype">Palatino Linotype</option>
                <option value="Segoe Print">Segoe Print</option>
                <option value="Segoe Script">Segoe Script</option>
                <option value="Segoe UI">Segoe UI</option>
                <option value="Segoe UI Light">Segoe UI Light</option>
                <option value="Segoe UI Semibold">Segoe UI Semibold</option>
                <option value="SimSun">SimSun</option>
                <option value="SimSun-ExtB">SimSun-ExtB</option>
                <option value="Sylfaen">Sylfaen</option>
                <option value="Tahoma">Tahoma</option>
                <option value="Times">Times</option>
                <option value="Times New Roman">Times New Roman</option>
                <option value="Trebuchet MS">Trebuchet MS</option>
                <option value="Verdana">Verdana</option>
            </select>
            <input type="number" name="size" style="width: 60px;" value="13">
            <button style="width: 30px;"><strong>B</strong></button>
            <button style="width: 30px;"><em><strong>I</strong></em></button>
            <button style="width: 30px;"><u><strong>U</strong></u></button>
        </div>
    </div>

    <div id="bottom">
        <div class="pressed">
            <button id="foreground" style="background-color: rgb(255, 0, 255);"></button>
            <button id="background" style="background-color: rgb(255, 255, 255);"></button>
        </div>
        <div id="color-palette">
            <button class="color" style="background-color: rgb(0, 0, 0);"></button>
            <button class="color" style="background-color: rgb(128, 128, 128);"></button>
            <button class="color" style="background-color: rgb(128, 0, 0);"></button>
            <button class="color" style="background-color: rgb(143, 143, 61);"></button>
            <button class="color" style="background-color: rgb(0, 100, 0);"></button>
            <button class="color" style="background-color: rgb(0, 139, 139);"></button>
            <button class="color" style="background-color: rgb(0, 0, 128);"></button>
            <button class="color" style="background-color: rgb(139, 0, 139);"></button>
            <button class="color" style="background-color: rgb(128, 128, 0);"></button>
            <button class="color" style="background-color: rgb(0, 128, 128);"></button>
            <button class="color" style="background-color: rgb(47, 79, 79);"></button>
            <button class="color" style="background-color: rgb(14, 4, 73);"></button>
            <button class="color" style="background-color: rgb(26, 12, 158);"></button>
            <button class="color" style="background-color: rgb(165, 42, 42);"></button>
            <button class="color" style="background-color: rgb(255, 255, 255);"></button>
            <button class="color" style="background-color: rgb(192, 192, 192);"></button>
            <button class="color" style="background-color: rgb(255, 0, 0);"></button>
            <button class="color" style="background-color: rgb(255, 255, 0);"></button>
            <button class="color" style="background-color: rgb(0, 128, 0);"></button>
            <button class="color" style="background-color: rgb(173, 255, 47);"></button>
            <button class="color" style="background-color: rgb(0, 0, 255);"></button>
            <button class="color" style="background-color: rgb(255, 0, 255);"></button>
            <button class="color" style="background-color: rgb(0, 255, 255);"></button>
            <button class="color" style="background-color: rgb(235, 255, 121);"></button>
            <button class="color" style="background-color: rgb(23, 245, 60);"></button>
            <button class="color" style="background-color: rgb(128, 0, 128);"></button>
            <button class="color" style="background-color: rgb(250, 128, 114);"></button>
            <button class="color" style="background-color: rgb(255, 165, 0);"></button>
        </div>
    </div>
    <div id="cursor-eraser"></div>
    <div id="image-placement"></div>
    </div>
</template>

<script>
// import $ from 'jquery';

export default {
    name: 'PaintWrapper',
    data() {
        return {
            canvas: null,
            ctx: null,
            lastX: 0,
            lastY: 0,
            back_fore_color: null,
            back_fore: null,
            color_change: null,
            func_buttons: [...document.querySelectorAll("#buttons button")],
            color_select: null,
            pressed: null,
            width: 10,
            isDrawing: false,
            isErase: false,
            isRect: false,
            isEllipse: false,
            isText: false,
            isFill: false,
            colorLayerData: null,
            menuSelected: "",
            canvasRect: null,
            cursorEraser: null,
            menu_items: null,
            sub_item_list: null,
            visible_menu: [],
            imageData: new Image(),
        }
    },
    methods: {
        draw(e) {
            if (!this.isDrawing){
                return
            }
            this.ctx.strokeStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.beginPath();
            this.ctx.moveTo(this.lastX, this.lastY);
            this.ctx.lineTo(e.offsetX, e.offsetY);
            this.ctx.stroke();
            [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
        },
        draw_rect(e){
            if(!this.isRect){return;}
            this.ctx.strokeStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.strokeRect(this.lastX, this.lastY, e.offsetX-this.lastX, e.offsetY-this.lastY);
            [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
        },
        draw_border_fill_rect(e){
            if(!this.isRect){return;}
            this.ctx.lineWidth=2;
            this.ctx.strokeRect(this.lastX, this.lastY, e.offsetX-this.lastX, e.offsetY-this.lastY);
            this.ctx.strokeStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.fillStyle=document.getElementById('background').style.backgroundColor;
            let x_coord = this.lastX < e.offsetX ? this.lastX+1 : e.offsetX+1;
            let y_coord = this.lastY < e.offsetY ? this.lastY+1 : e.offsetY+1;
            let x_width= this.lastX < e.offsetX? Math.abs(e.offsetX-this.lastX-2) : Math.abs(e.offsetX-this.lastX+2);
            let y_width = this.lastY < e.offsetY ? Math.abs(e.offsetY-this.lastY-2) : Math.abs(e.offsetY-this.lastY+2);
            this.ctx.fillRect(x_coord, y_coord, x_width, y_width);
            [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
        },
        draw_fill_rect(e){
            if(!this.isRect){return;}
            this.ctx.fillStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.fillRect(this.lastX, this.lastY, e.offsetX-this.lastX, e.offsetY-this.lastY);
            [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
        },
        draw_ellipse(e){
            if(!this.isEllipse){return;}
            let x_center = e.offsetX < this.lastX ? e.offsetX + (Math.abs(e.offsetX-this.lastX)/2) : this.lastX + (Math.abs(e.offsetX-this.lastX)/2);
            let y_center = e.offsetY < this.lastY ? e.offsetY + (Math.abs(e.offsetY-this.lastY)/2) : this.lastY + (Math.abs(e.offsetY-this.lastY)/2);
            this.ctx.lineWidth=2;
            this.ctx.strokeStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.beginPath();
            this.ctx.ellipse(x_center, y_center, Math.abs(e.offsetX-this.lastX), Math.abs(e.offsetY-this.lastY), 0, 0, 2*Math.PI);
            this.ctx.stroke();
        },
        draw_border_fill_ellipse(e){
            if(!this.isEllipse){return;}
            this.draw_ellipse(e);
            this.ctx.strokeStyle = document.getElementById('foreground').style.backgroundColor;
            this.ctx.fillStyle = document.getElementById('background').style.backgroundColor;
            let x_center= e.offsetX < this.lastX ? e.offsetX + (Math.abs(e.offsetX-this.lastX)/2) : this.lastX+(Math.abs(e.offsetX-this.lastX)/2);
            let y_center = e.offsetY < this.lastY ? e.offsetY + (Math.abs(e.offsetY-this.lastY)/2) : this.lastY+(Math.abs(e.offsetY-this.lastY)/2);
            this.ctx.beginPath();
            let x_radius = e.offsetX < this.lastX ? Math.abs(e.offsetX - this.lastX+1) : Math.abs(e.offsetX-this.lastX-1);
            let y_radius = e.offsetY < this.lastY ? Math.abs(e.offsetY-this.lastY+1):Math.abs(e.offsetY-this.lastY-1);
            this.ctx.ellipse(x_center, y_center, x_radius, y_radius, 0, 0, 2*Math.PI);
            this.ctx.fill();
        },
        draw_fill_ellipse(e){
            if(!this.isEllipse){return;}
            let x_center = e.offsetX < this.lastX ? e.offsetX + (Math.abs(e.offsetX-this.lastX)/2) : this.lastX+(Math.abs(e.offsetX-this.lastX)/2);
            let y_center = e.offsetY < this.lastY ? e.offsetY + (Math.abs(e.offsetY-this.lastY)/2) : this.lastY+(Math.abs(e.offsetY-this.lastY)/2);
            this.ctx.fillStyle=document.getElementById('foreground').style.backgroundColor;
            this.ctx.beginPath();
            this.ctx.ellipse(x_center, y_center, Math.abs(e.offsetX-this.lastX), Math.abs(e.offsetY-this.lastY), 0, 0, 2*Math.PI);
            this.ctx.fill();
        },
        wrapText(text, x, y, maxWidth) {
            let words = text.split(' ');
            let line = '';

            for(let n = 0; n < words.length; n++) {
                let testLine = line + words[n] + ' ';
                let testWidth = this.ctx.measureText(testLine).width;
                if (testWidth > maxWidth && n > 0) {
                    this.ctx.fillText(line, x, y);
                    line = words[n] + ' ';
                    y += 25;
                }else {line = testLine;}
            }
            this.ctx.fillText(line, x, y);
        },
        draw_text(){
            let textArea=[...document.querySelectorAll('textarea')];

            textArea.map(area=>{
                area.style.zIndex='-1';
                area.style.borderStyle="none";
                this.ctx.fillStyle=`${document.getElementById('foreground').style.backgroundColor}`;
                this.ctx.font=`${area.style.fontSize} ${area.style.fontFamily}`;
                if(area.style.fontWeight==='bolder'){this.ctx.font="bold "+this.ctx.font;}
                if(area.style.fontStyle==='italic'){this.ctx.font="italic "+this.ctx.font;}
                this.wrapText(area.value, area.offsetLeft, area.offsetTop, parseFloat(area.style.width.substr(0, area.style.width.length-2)));
                area.remove();
            });
        },
        match_start_color(pixelPos, startColor){
            let r = this.colorLayerData.data[pixelPos];
            let g = this.colorLayerData.data[pixelPos+1];
            let b = this.colorLayerData.data[pixelPos+2];
            let a = this.colorLayerData.data[pixelPos+3];
            return (r==startColor[0] && g==startColor[1] && b==startColor[2] && a==startColor[3]);
        },
        color_pixel(pixelPos, colorRGB){
            this.colorLayerData.data[pixelPos]=colorRGB[0];
            this.colorLayerData.data[pixelPos+1]=colorRGB[1];
            this.colorLayerData.data[pixelPos+2]=colorRGB[2];
            this.colorLayerData.data[pixelPos+3]=colorRGB[3];
        },
        closeMenus(){
            let to_inactive=this.visible_menu.shift();
            to_inactive.querySelector('li').classList.remove('active');
            this.sub_item_list.map(sub_item=>sub_item.style.visibility="hidden");
        },
        newCanvas(){
            window.location.reload();
        },
        openFile() {
            const input = document.createElement("input");
            input.type = "file";
            input.accept = "./../assets/*";
            input.click();
            input.addEventListener("change", (event) => {
            this.readSelectedImage(event.target.files[0]);
            input.remove();
            });
        },
        readSelectedImage(uploadedImage) {
            const fReader = new FileReader();
            fReader.onload = (e) => {
                this.imageData.onload = () => {
                    this.closeMenus();
                    const drawRatios = this.calculateImageRatios(this.imageData.width,this.imageData.height);
                    const imgPlacementDiv = document.querySelector('#image-placement'); 
                    imgPlacementDiv.style.width = drawRatios.width + 'px';
                    imgPlacementDiv.style.height = drawRatios.height + 'px';
                    imgPlacementDiv.style.display = "block";
                    this.canvas.addEventListener('mousemove', this.updateImagePlacementDiv);
                    this.canvas.addEventListener('click',this.imagePlaceClick);
                };
                this.imageData.src = e.target.result;
            };
            fReader.readAsDataURL(uploadedImage);
        },
        updateImagePlacementDiv(e){
            const imgPlacementDiv = document.querySelector('#image-placement'); 
            const x = e.clientX;
            const y = e.clientY;
            imgPlacementDiv.style.top = y + 'px';
            imgPlacementDiv.style.left = x + 'px';
        },
        imagePlaceClick(e){
            const x = e.clientX - 70;
            const y = e.clientY - 25;
            this.loadImageOntoCanvas(this.imageData,x,y);
            this.canvas.removeEventListener('click', this.imagePlaceClick);
            this.canvas.removeEventListener('mousemove', this.updateImagePlacementDiv);
            document.querySelector('#image-placement').style.display = "none";
        },
        loadImageOntoCanvas(image, x, y) {
            const drawRatios = this.calculateImageRatios(image.width,image.height);

            this.ctx.drawImage(image, x, y, drawRatios.width, drawRatios.height);
        },
        calculateImageRatios(width,height){
            let drawWidth = width;
            let drawHeight = height;
            if(width > this.canvas.width){
                let ratio = this.canvas.width / width;
                drawWidth = this.canvas.width;
                drawHeight = height * ratio;
            }
            if(height > this.canvas.height){
                let ratio = this.canvas.height / height;
                drawHeight = this.canvas.height;
                drawWidth = width * ratio;
            }
            return {
                width:drawWidth,
                height:drawHeight
            };
        }
    },
    mounted: function(){

        this.canvas = document.getElementById('canvas');

        this.ctx = this.canvas.getContext('2d');
        
        this.back_fore_color = document.getElementById('foreground');
        this.back_fore = document.querySelectorAll('.pressed button');
        this.color_change = document.querySelectorAll(".color");
        this.func_buttons = [...document.querySelectorAll("#buttons button")];
        
        this.color_select = document.getElementById('color-select');
        
        this.colorLayerData= this.ctx.getImageData(0, 0, 1920, 850);
        this.canvasRect = this.canvas.getBoundingClientRect();
        this.cursorEraser = document.getElementById('cursor-eraser');
        this.menu_items = [...document.querySelectorAll('#main-menu > div')];
        this.sub_item_list = [...document.querySelectorAll('ul.menu')];
        console.log(this.cursorEraser)
        this.back_fore.forEach(b_f=>{
            b_f.addEventListener('click', ()=>{
                this.back_fore_color=b_f
                
                this.ctx.strokeStyle=this.back_fore_color.style.backgroundColor;
            });
        });

        this.color_change.forEach(color=>{
            color.addEventListener('click', ()=>{
                let col=color.style.backgroundColor;
                this.back_fore_color.style.backgroundColor=col;
                this.ctx.strokeStyle=col;
            });
        });

        this.ctx.strokeStyle = this.back_fore_color.style.backgroundColor;

        this.cursorEraser.style.width = this.width + "px";

        this.cursorEraser.style.height = this.width + "px";

        document.addEventListener('mousemove', (event) => {
            if(this.menuSelected === "eraser"){
                let mouseY = event.clientY;
                let mouseX = event.clientX;
                this.cursorEraser.style.top = mouseY + 'px';
                this.cursorEraser.style.left = mouseX + 'px';

                if(mouseY < this.canvasRect.top || mouseY > this.canvasRect.bottom || mouseX < this.canvasRect.left || mouseX > this.canvasRect.right){
                    this.cursorEraser.style.display = "none";
                }
                else{
                    this.cursorEraser.style.display = "block";
                }
            }
        });

        this.func_buttons.forEach(button=>{
            button.addEventListener('click', ()=>{

                this.menuSelected = "";

                document.getElementById('color-select').style.backgroundColor="#bbc6c9";
                document.getElementById('text-editor').style.visibility="hidden";
                this.cursorEraser.style.display = "none";

                this.isDrawing=false;
                this.isErase=false;
                this.isRect=false;
                this.isEllipse=false;

                this.isText=false;
                this.isFill=false;

                if(button.firstChild === this.pressed){
                    this.pressed=null;
                    button.removeAttribute('id');
                }else{
                    this.pressed=button.firstChild;
                    this.func_buttons.map(button=>button.removeAttribute('id'));
                    button['id']='btn-pressed';
                }

                this.canvas.style.cursor='default';

                this.isDrawing=false;
                while(this.color_select.hasChildNodes()){this.color_select.removeChild(this.color_select.firstElementChild);}

                if(button['title']==='Eraser/Color Eraser' && button['id']==='btn-pressed'){
                    this.menuSelected = "eraser";

                    this.cursorEraser.style.display = "block";

                    document.addEventListener('keydown', (e)=>{
                        if(e.keyCode===107){++this.width;}
                        if(this.width!==3 && e.keyCode===109){--this.width;}
                        this.cursorEraser.style.width = this.width + "px";
                        this.cursorEraser.style.height = this.width + "px";
                    });

                    this.draw_text();

                    this.canvas.addEventListener('mousedown', (e)=>{
                        this.isDrawing=false;
                        this.isRect=false;
                        this.isErase=true;
                        this.isEllipse=false;
                        this.isText=false;
                        this.isFill=false;
                        [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
                    });

                    this.canvas.addEventListener('mousemove', (e)=>{
                        if(!this.isErase){return;}
                        this.ctx.clearRect(e.offsetX, e.offsetY, this.width, this.width);
                    });

                    this.canvas.addEventListener('mouseout', ()=>this.isErase=false);
                    this.canvas.addEventListener('mouseup', ()=>this.isErase=false);

                }else if(button['title']==='Fill With Color' && button['id']==='btn-pressed'){

                    this.canvas.addEventListener('mousedown', ()=>{
                        this.isDrawing=false;
                        this.isRect=false;
                        this.isErase=false;
                        this.isEllipse=false;
                        this.isText=false;
                        this.isFill=true;
                    });

                    this.canvas.addEventListener('mouseup', (e)=>{
                        if(!this.isFill){return;}
                        this.colorLayerData=this.ctx.getImageData(0, 0, 1920, 850);
                        this.ctx.fillStyle=document.getElementById('foreground').style.backgroundColor;
                        let foreground=document.getElementById('foreground').style.backgroundColor.split(', ');
                        let fillRed=parseFloat(foreground[0].substring(4, foreground[0].length));
                        let fillGreen=parseFloat(foreground[1]);
                        let fillBlue=parseFloat(foreground[2].substring(0, foreground[2].length-1));

                        let currColor=this.ctx.getImageData(e.offsetX, e.offsetY, 1, 1).data;
                        let colorRGB=[fillRed, fillGreen, fillBlue, 255];
                        if(currColor[0]===fillRed && currColor[1]===fillGreen && currColor[2]===fillBlue && currColor[3]===255){return;}
                        let pixelStack = [[e.offsetX, e.offsetY]];
                        while(pixelStack.length){
                            let newPos=pixelStack.pop();
                            let x=newPos[0];
                            let y=newPos[1];
                            let pixelPos=(y*1920+x)*4;

                            while(y-->=0 && this.match_start_color(pixelPos, currColor)){pixelPos-=1920*4;}
                            pixelPos+=1920*4;
                            ++y;
                            let reachLeft=false;
                            let reachRight=false;
                            while(y++<850 && this.match_start_color(pixelPos, currColor)){
                                this.color_pixel(pixelPos, colorRGB);
                                if(x>0){
                                    if(this.match_start_color(pixelPos-4, currColor)){
                                        if(!reachLeft){
                                            pixelStack.push([x-1, y]);
                                            reachLeft=true;
                                        }
                                    }else if(reachLeft){reachLeft=false;}
                                }
                                if(x<1920){
                                    if(this.match_start_color(pixelPos+4, currColor)){
                                        if(!reachRight){
                                            pixelStack.push([x+1, y]);
                                            reachRight=true;
                                        }
                                    }else if(reachRight){reachRight=false;}
                                }
                                pixelPos+=1920*4;
                            }
                        }
                        this.ctx.putImageData(this.colorLayerData, 0 ,0);
                    });


                }else if(button['title']==='Pencil' && button['id']==='btn-pressed'){

                    this.ctx.lineCap='round';
                    this.ctx.lineJoin='round';
                    this.ctx.lineWidth=1;

                    this.draw_text();

                    this.canvas.addEventListener('mousedown', (e)=>{
                        this.isDrawing=true;
                        this.isErase=false;
                        this.isRect=false;
                        this.isEllipse=false;
                        this.isText=false;
                        this.isFill=false;
                        [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
                    });

                    this.canvas.addEventListener('mousemove', this.draw, true);
                    this.canvas.addEventListener('mouseout', ()=>this.isDrawing=false);
                    this.canvas.addEventListener('mouseup', ()=>this.isDrawing=false);

                }else if(button['title']==="Text" && button['id']==='btn-pressed'){

                    this.canvas.style.cursor="crosshair";

                    this.canvas.addEventListener('mousedown', (e)=>{
                        this.isText=true;
                        this.isDrawing=false;
                        this.isEllipse=false;
                        this.isRect=false;
                        this.isEllipse=false;
                        this.isErase=false;
                        this.isFill=false;
                        [this.lastX, this.lastY]=[e.clientX, e.clientY];
                    });

                    this.canvas.addEventListener('mouseout', ()=>this.isText=false);
                    this.canvas.addEventListener('mouseup', (e)=>{

                        if(!this.isText){return;}
                        let textArea=document.createElement('textarea');
                        textArea.style.width=`${Math.abs(this.lastX-e.clientX)}px`;
                        textArea.style.height=`${Math.abs(this.lastY-e.clientY)}px`;
                        textArea.style.position="absolute";
                        textArea.style.left=`${this.lastX < e.offsetX ? this.lastX : e.clientX}px`;
                        textArea.style.top=`${this.lastY < e.offsetY ? this.lastY : e.clientY}px`;
                        textArea.style.outline="none";
                        textArea.style.borderStyle="dashed";
                        document.getElementById('canvas-container').appendChild(textArea);

                        textArea.addEventListener("focus", ()=>{
                            document.getElementById('text-editor').style.visibility="visible";
                            textArea.style.fontFamily=document.getElementById('fonts').value;
                            textArea.style.fontSize=`${document.getElementsByName('size')[0].value}px`;
                            textArea.style.color=document.getElementById('foreground').style.backgroundColor;

                            let bold=true, italic=true, underline=true;

                            document.getElementById('text-editor').querySelectorAll("button").forEach(styleButton=>{
                                styleButton.addEventListener('click', ()=>{
                                    if(styleButton===document.getElementById('text-editor').querySelectorAll("button")[0]){
                                        if(!bold){textArea.style.fontWeight="normal";}
                                        else{textArea.style.fontWeight="bolder";}
                                        bold=(!bold);
                                    }else if(styleButton===document.getElementById('text-editor').querySelectorAll("button")[1]){
                                        if(!italic){textArea.style.fontStyle="normal";}
                                        else{textArea.style.fontStyle="italic";}
                                        italic=(!italic);
                                    }else if(styleButton===document.getElementById('text-editor').querySelectorAll("button")[2]){
                                        if(!underline){textArea.style.textDecoration="none";}
                                        else{textArea.style.textDecoration="underline";}
                                        underline=(!underline);
                                    }
                                });
                            });
                        });

                        [this.lastX, this.lastY]=[e.clientX, e.clientY];
                    });

                }else if(button['title']==='Line' && button['id']==='btn-pressed'){

                    this.canvas.style.cursor="crosshair";
                    this.ctx.lineCap='round';
                    this.ctx.lineJoin='round';
                    this.ctx.lineWidth=1;

                    this.draw_text();

                    this.canvas.addEventListener('mousedown', (e)=>{
                        this.isDrawing=true;
                        this.isErase=false;
                        this.isRect=false;
                        this.isEllipse=false;
                        this.isFill=false;
                        [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
                    });

                    this.canvas.removeEventListener('mousemove', this.draw, true);
                    this.canvas.addEventListener('mouseout', ()=>this.isDrawing=false);
                    this.canvas.addEventListener('mouseup', this.draw, true);

                }else if(button['title']==='Rectangle' && button['id']==='btn-pressed'){

                    this.canvas.style.cursor="crosshair";

                    let rect_borderless=document.createElement('button');
                    rect_borderless.classList.add('inner-div');
                    rect_borderless.innerHTML="<img src='./../assets/rectangle.png'>";
                    rect_borderless.firstElementChild.style.width='34px';
                    rect_borderless.style.width='44px';
                    rect_borderless.firstElementChild.style.height='20px';
                    rect_borderless.style.marginLeft='2px';
                    this.color_select.appendChild(rect_borderless);

                    let rect_border=document.createElement('button');
                    rect_border.classList.add('inner-div');
                    rect_border.innerHTML="<img src='./../assets/border-rectangle.png'>";
                    rect_border.style.position='absolute';
                    rect_border.style.top='30px';
                    rect_border.style.left='2px';
                    rect_border.firstElementChild.style.width='34px';
                    rect_border.style.width='44px';
                    rect_border.firstElementChild.style.height='15px';
                    this.color_select.appendChild(rect_border);

                    let rect_fill=document.createElement('button');
                    rect_fill.classList.add('inner-div');
                    rect_fill.innerHTML="<img src='./../assets/fill-rectangle.png'>";
                    rect_fill.style.position='absolute';
                    rect_fill.style.top='57px';
                    rect_fill.style.left='2px';
                    rect_fill.firstElementChild.style.width='34px';
                    rect_fill.style.width='44px';
                    rect_fill.firstElementChild.style.height='15px';
                    this.color_select.appendChild(rect_fill);

                    let button_list=[...document.querySelectorAll('.inner-div')];

                    this.draw_text();

                    this.canvas.addEventListener('mousedown', ()=>{
                        this.isDrawing=false;
                        this.isErase=false;
                        this.isEllipse=false;
                        this.isText=false;
                        this.isFill=false;
                    });

                    this.button_list.forEach(button=>{
                        button.addEventListener('click', ()=>{

                            button_list.map(button=>button.removeAttribute('id'));
                            button_list[0].innerHTML="<img src='./../assets/rectangle.png'>";
                            button_list[0].firstElementChild.style.width='38px';
                            button_list[0].firstElementChild.style.height='20px';
                            button['id']='btn-active';

                            this.canvas.addEventListener('mousedown', (e)=>{
                                this.isRect=true;
                                [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
                            });
                            this.canvas.addEventListener('mouseout', ()=>this.isRect=false);

                            if(button===button_list[0]){
                                button.innerHTML="<img src='./../assets/white-border-rect.png'>";
                                button.firstElementChild.style.width='38px';
                                button.firstElementChild.style.height='20px';
                                this.canvas.removeEventListener('mouseup', this.draw_border_fill_rect, true);
                                this.canvas.removeEventListener('mouseup', this.draw_fill_rect, true);
                                this.canvas.addEventListener('mouseup', this.draw_rect, true);

                            }else if(button===button_list[1]){
                                this.canvas.removeEventListener('mouseup', this.draw_rect, true);
                                this.canvas.removeEventListener('mouseup', this.draw_fill_rect, true);
                                this.canvas.addEventListener('mouseup', this.draw_border_fill_rect, true);

                            }else if(button===button_list[2]){
                                this.canvas.removeEventListener('mouseup', this.draw_rect, true);
                                this.canvas.removeEventListener('mouseup', this.draw_border_fill_rect, true);
                                this.canvas.addEventListener('mouseup', this.draw_fill_rect, true);
                            }

                        });

                    });

                    this.ctx.lineWidth=1;

                }else if(button['title']==='Ellipse' && button['id']==='btn-pressed'){

                    this.canvas.style.cursor="crosshair";

                    this.draw_text();

                    let ellipse_borderless=document.createElement('button');
                    ellipse_borderless.classList.add('inner-div');
                    ellipse_borderless.innerHTML="<img src='./../assets/ellipse_borderless.png'>";
                    ellipse_borderless.firstElementChild.style.width='34px';
                    ellipse_borderless.style.width='44px';
                    ellipse_borderless.firstElementChild.style.height='17px';
                    ellipse_borderless.style.marginLeft='2px';
                    this.color_select.appendChild(ellipse_borderless);

                    let ellipse_border=document.createElement('button');
                    ellipse_border.classList.add('inner-div');
                    ellipse_border.innerHTML='<img src="./../assets/ellipse_borderless.png">';
                    ellipse_border.style.position='absolute';
                    ellipse_border.style.top='30px';
                    ellipse_border.style.left='2px';
                    ellipse_border.firstElementChild.style.width='34px';
                    ellipse_border.style.width='44px';
                    ellipse_border.firstElementChild.style.height='15px';
                    this.color_select.appendChild(ellipse_border);

                    let ellipse_fill=document.createElement('button');
                    ellipse_fill.classList.add('inner-div');
                    ellipse_fill.innerHTML="<img src='./../assets/ellipse_fill.png'>";
                    ellipse_fill.style.position='absolute';
                    ellipse_fill.style.top='57px';
                    ellipse_fill.style.left='2px';
                    ellipse_fill.firstElementChild.style.width='34px';
                    ellipse_fill.style.width='44px';
                    ellipse_fill.firstElementChild.style.height='15px';
                    this.color_select.appendChild(ellipse_fill);

                    let button_list=[...document.querySelectorAll('.inner-div')];

                    this.canvas.addEventListener('mousedown', ()=>{
                        this.isRect=false;
                        this.isDrawing=false;
                        this.isErase=false;
                        this.isText=false;
                        this.isFill=false;
                    });

                    button_list.forEach(button=>{
                        button.addEventListener('click', ()=>{

                            button_list.map(button=>button.removeAttribute('id'));
                            button['id']='btn-active';

                            this.canvas.addEventListener('mousedown', (e)=>{
                                this.isEllipse=true;
                                [this.lastX, this.lastY]=[e.offsetX, e.offsetY];
                            });

                            this.canvas.addEventListener('mouseout', ()=>this.isEllipse=false);

                            if(button===button_list[0]){
                                this.canvas.addEventListener('mouseup', this.draw_ellipse, true);
                                this.canvas.removeEventListener('mouseup', this.draw_border_fill_ellipse, true);
                                this.canvas.removeEventListener('mouseup', this.draw_fill_ellipse, true);

                            }else if(button===button_list[1]){
                                this.canvas.removeEventListener('mouseup', this.draw_ellipse, true);
                                this.canvas.addEventListener('mouseup', this.draw_border_fill_ellipse, true);
                                this.canvas.removeEventListener('mouseup', this.draw_fill_ellipse, true);
                            }else if(button===button_list[2]){
                                this.canvas.removeEventListener('mouseup', this.draw_ellipse, true);
                                this.canvas.removeEventListener('mouseup', this.draw_border_fill_ellipse, true);
                                this.canvas.addEventListener('mouseup', this.draw_fill_ellipse, true);
                            }

                        });

                    });

                    this.ctx.lineWidth=1;

                }else{

                    this.draw_text();

                    this.canvas.addEventListener('mousedown', ()=>{
                        this.isDrawing=false;
                        this.isErase=false;
                        this.isRect=false;
                        this.isEllipse=false;
                        this.isText=false;
                        this.isFill=false;
                    });
                }

            });
        });

        document.querySelector('#bottom .pressed').addEventListener('contextmenu', (e)=>{
            e.preventDefault();
            let temp=document.getElementById('foreground').style.backgroundColor;
            document.getElementById('foreground').style.backgroundColor=document.getElementById('background').style.backgroundColor;
            document.getElementById('background').style.backgroundColor=temp;
        });

        this.menu_items.forEach(item=>{
            item.querySelector('li').addEventListener('click', ()=>{
                if(this.visible_menu.length!==0){
                    let to_hide=this.visible_menu.shift();
                    to_hide.querySelector('li').classList.remove('active');
                    to_hide.querySelector('ul.menu').style.visibility="hidden";
                    if(to_hide===item){return;}
                }
                this.sub_item_list[this.menu_items.indexOf(item)].style.visibility="visible";
                this.visible_menu.push(this.menu_items[this.menu_items.indexOf(item)]);
                item.querySelector('li').classList.add('active');   
            });
        });

        this.canvas.addEventListener('click', ()=>{
            this.closeMenus();
        });

        window.addEventListener('mousemove', (e)=>document.getElementById('cursor-pos').textContent=`${e.clientX}x${e.clientY}`);

        document.getElementById('save').addEventListener('click', ()=>{
            document.getElementById('save').href=this.canvas.toDataURL();
            document.getElementById('save').download="js_canvas.png";
        });

    }
}
</script>

<style>
    *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body{
    overflow: hidden;
}

div{
    background-color: #bbc6c9;
    height: 25px;
    font-family: 'Dosis', sans-serif;
    border-bottom: 1px outset #bbc6c9;
}

ul{
    list-style: none;
    padding-top: 3px;
    margin-left: 10px;
}

ul div{
    height: 22px;
    width: 50px;
}

li{
    width: 60px;
    float: left;
    cursor: pointer;
    text-align: center;
}

button{
    width: 50%;
    height: 30px;
    border: 1px outset;
    background-color: #bbc6c9;
    outline: none;
    box-shadow: 1px 1px black;
}

img{
    width: 20px;
}

input{
    width: 125px;
    z-index: 10;
}

canvas{
    position: absolute;
    top: 25px;
    left: 70px;
    overflow: scroll;
}

span{
    text-decoration: underline;
}

button.color{
    position: relative;
    height: 15px;
    width: 15px;
    border: 0.5px inset #e3e6e7;
}

button.inner-div{
    height: 14px;
    width: 15px;
    border: none;
    box-shadow: none;
    padding-bottom: 15px;
    text-align: center;
}

.menu{
    display: flex;
    visibility: hidden;
    flex-direction: column;
    width: 140px;
    padding: 5px;
    background-color: #bbc6c9;
    position: relative;
    border: 1px outset #818283;
    z-index: 1;
}

ul.menu a li{
    float: none;
    width: 130px;
    text-align: left;
    padding-left: 30px;
}

ul.menu a:hover{
    background-color: navy;
    color: white;
}

ul.menu a{
    text-decoration: none;
    color: black;
}

#btn-pressed{
    border: 1px inset white;
    background-color: #e3e6e7;
}

#head:hover{
    background-color: navy;
    cursor: pointer;
}

.pressed{
    height: 40px;
    width: 40px;
    border: 1px inset white;
    background-color: #e3e6e7;
    margin-left: 28px;
    margin-top: 15px;
}

.active{
    border: 1px inset white;
    background-color: #e3e6e7;
}

#sidebar{
    height: 84vh;
    width: 70px;
    border-right: 1px outset #bbc6c9;
    padding-top: 20px;
    border-top: 1px outset #eaedee;
    transition: transform 0.2s ease-in;
}

#buttons{
    display: flex;
    flex-wrap: wrap;
    margin-left: 5px;
    margin-right: 5px;
}

#color-select{
    height: 80px;
    width: 50px;
    position: relative;
    top: 250px;
    left: 10px;
    border-bottom: 1px solid rgb(230, 228, 228);
    border-right: 1px solid rgb(230, 228, 228);
    border-left: 1.5px solid rgb(177, 177, 177);
    border-top: 1.5px solid rgb(177, 177, 177);
    display: flex;
    flex-wrap: wrap;
}

#bottom{
    position: relative;
    top: 0;
    height: 75px;
    border-top: 1px outset #eaedee;
    display: flex;
    transition: transform 0.2s ease-in;
}

#foreground{
    position: relative;
    height: 18px;
    width: 18px;
    left: 4px;
    top: 3px;
    z-index: 2;
    border: 1px solid #e3e6e7;
}

#background{
    position: relative;
    height: 18px;
    width: 18px;
    left: 12px;
    bottom: 7px;
    border: 1px solid #e3e6e7;
}

#color-palette{
    width: 260px;
    height: 55px;
    margin-left: 3px;
    margin-top: 15px;
}

#cursor-pos, #draw-size{
    width: 10%;
    text-align: right;
}

#main-menu{
    display: flex;
    flex: 1;
}

#btn-active{
    background-color: navy;
    color: white;
}

#btn-active i{
    color: white;
}

#text-editor{
    position: absolute;
    left: 35%;
    top: 50%;
    height: 2.5em;
    width: 339px;
    padding-left: 5px;
    padding-top: 3px;
    border: 1px outset #818283;
    box-shadow: 2px 2px #e3e6e7;
    visibility: hidden;
}

#canvas-container{
    height: 0;
    overflow-y: scroll;
}

#canvas{
    transition: transform 0.2s ease-in;
}

.canvas-left{
    transform: translateX(-70px);
}

#cursor-eraser{
    position: absolute;
    border-color: black;
    background: rgba(0,0,0,0);
    border-width: 2px;
    border-style: solid;
    display:none;
    pointer-events: none; /*Permit to click below this div*/
}


#image-placement{
    width:0px;
    height:0px;
    border:1px dashed #aaa;
    background-color: rgba(0,0,0,0.05);
    display:none;
    position:fixed;
    pointer-events:none;
}

</style>