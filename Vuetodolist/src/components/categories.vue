<script setup >

</script>

<template>
    <h3>Welcome Back!</h3>
    <div class="categories" >
    <h2>Categories</h2>
    <br>
    <div class="tabs" >
        <div class="list 1" >
            <p>Shopping List</p>
           <div class="task-num" >
               9 Task
           </div>
        </div>
        <div class="list 2" >
            <p>Gym Workouts</p>
            <div class="task-num" >
                9 Task
            </div>
        </div>
        <div class="list 3" >
            <p>Shopping</p>
            <div class="task-num" >
                9 Task
            </div>
        </div>
    </div>
</div>

</template>


<style scoped >

    .list{
        background: #FFFFFF;
box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
border-radius: 20px;
margin-right: 19px;
width: 155px;
height: 108px;
padding:18px;
    }

    p{
        font-family: 'Inter';
        font-style: normal;
        font-weight: 700;
        font-size: 24px;
        line-height: 29px;
        width: fit-content;
        color: #000000;
        
    }
    .task-num{
        bottom: 0px;
font-family: 'Inter';
font-style: normal;
font-weight: 400;
font-size: 11px;
line-height: 13px;

color: #808080;

    }

    .tabs{
        height: 110px;
        width: 503px;
        display: flex;
        flex-direction: row;
        overflow-x: scroll;
        overflow-y: hidden;
        margin-top: 10px;
    }

    .categories{
        width: 100%;
    height: fit-content;
    overflow: scroll;
    }

    h3{
        font-family: 'Inter';
font-style: normal;
font-weight: 600;
font-size: 32px;
line-height: 39px;
margin-bottom: 36px;
color: #2F2F2F;

    }

h2{
    width: fit-content;
    padding-left: 25px;
    margin-bottom: 20px;
position: absolute;
height: 21px;
    font-family: 'Inter';
font-style: normal;
font-weight: 700;
font-size: 15px;
line-height: 18px;
text-transform: uppercase;

color: #808080;
}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    overflow: hidden;
}
</style>