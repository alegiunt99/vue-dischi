<template>
    <select name="songs-type" class="col-1" >
        <option value="">All</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
    </select>
</template>

<script>
export default {

    name: 'MusicType',

    props:{
    }

}
</script>

<style lang="scss" scoped>
    select{
            padding: 7px;
            border-radius: 10px;
            color: white;
            background-color: #2e3a46;
            margin-top: 35px;
            border: none;
            font-size: 17px;
        }
</style>