<template>
    <div>
        <label for="music">Filter by gender</label>
        <select v-model = "selected" @change="$emit('valueChange', selected)" name="music" id="music">
            <option v-for="(option, index) in options" :key= "index" :value = "option.value">{{option.text}}</option>
        </select>
        <span>selected:{{selected}}</span>
    </div>
</template>

<script>
export default {
    name: 'Select',
    data(){
        return{
            selected:'',
            options:[
            {
                text: 'All', value:'all'
            },
            {
                text: 'Pop', value:'pop'
            },
            {
                text: 'Jazz', value:'jazz'
            },
            {
                text: 'Rock', value:'rock'
            },
            {
                text: 'Metal', value:'metal'
            },
            ],
            
        }
    }
}

</script>

<style scoped lang="scss">
label{
    color:white;
    margin-right: 5px;
}
select{
    border-radius:5px;
}

</style>