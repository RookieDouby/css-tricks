<template>
    <div class="container">
        <div class="content nth-child-content">
            <ul>
                <li>1</li>
                <li>2</li>
                <li>3</li>
                <li>4</li>
                <li>5</li>
                <li>6</li>
                <li>7</li>
                <li>8</li>
                <li>9</li>
                <li>10</li>
                <li>11</li>
            </ul>
        </div>
        <div class="content vertical-text">
            <h3>将进酒</h3>
            <p>君不见，黄河之水天上来，奔流到海不复回。</p>
            <p>君不见，高堂明镜悲白发，朝如青丝暮成雪。</p>
        </div>
        <div class="content not-use">
            <h3>三、:not()灵活运用</h3>
            <div class="first-line">
                <span>A</span>
                <span>B</span>
                <span>C</span>
                <span>D</span>
                <span>E</span>
            </div>
            <div class="second-line">
                <span>A</span>
                <span>B</span>
                <span>C</span>
                <span>D</span>
                <span>E</span>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    html,body {
        margin: 0;
        padding: 0;
    }
    .container {
        .content {
            padding: 30px 0;
            border-bottom: 1px solid #000; 
            width: 100%;
            &:nth-child(1) {
                padding-top: 0;
            }
            &.nth-child-content {
                ul {
                    width: 300px;
                    margin: 0 auto;
                    list-style: none;
                    text-align:center;
                    li {
                        cursor: pointer;
                        padding: 10px 0;
                        &:nth-child(2n+1) {
                            background: red;
                        }
                        &:nth-child(2n) {
                            background: blue;
                        }
                        &:nth-child(n+6):nth-child(-n+10){
                            background: green;
                        }
                    }
                }
            }
            &.vertical-text {
                writing-mode: vertical-rl;
            }
            &.not-use {
                .first-line {                    
                    span:not(:last-child)::after {
                        content: ",";
                        margin-right: 3px;
                    }
                }
                .second-line {                    
                    span:not(:nth-child(-n+3)) {
                        content: ",";
                        display: none;
                    }
                }
            }
        }
    }
</style>