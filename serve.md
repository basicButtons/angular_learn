
获取数据的方式：
    1.在app.module.ts 中引入 HttpClientModule

    import { HttpClientModule } from '@angular/common/http'

    imports: [
    BrowserModule,
    HttpClientModule
    ]

    2.在app.component.ts 中引入  HttpClient 同时引入 OnInit

    import { HttpClient } from '@angular/common/http';
    import { Component, OnInit} from '@angular/core';

    自己 加上构造器 然后 implements OnInit

    export class AppComponent implements OnInit{
        title = 'server';
        constructor(private http:HttpClient){

    }
    ngOnInit(){
        this.http.get("https://jsonplaceholder.typicode.com/photos") //这一行得到的就是一个observeable
        .subscribe( data => {
        console.log(data);
        } )//这个地方就是订阅
    }
    }