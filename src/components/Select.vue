<template>
    <div>
        <label for="music">Filter by gender</label>
        <select name="music" id="music">
            <option value="Pop">All</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Rock">Rock</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'Select',
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