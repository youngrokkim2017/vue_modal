<template>
    <div class="backdrop" @click.self="closeModal"> <!-- to add modifier .modifier -->
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <!-- <h1>{{ header }}</h1> -->
            <!-- <p>{{ text }}</p> -->

            <!-- SLOT -->            
            <slot></slot>

            <!-- specific name SLOT -->  
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    // props: ['header', 'text', 'theme'],
    props: ['theme'],
    methods: {
        closeModal() {
            // emit an event
            this.$emit('close')
        }
    }
}
</script>


<style>
/* <style scoped> */
    .modal {
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    .modal h1 {
        color: #03cfb4;
        border: none;
        padding: 0;
    }
    .modal p {
        font-style: none;
    }
    .modal.sale {
        background: crimson;
        color: white;
    }
    .modal.sale h1 {
        color: white;
    }
    .modal .actions {
        text-align: center;
        margin: 30px 0 10px 0;
    }
    .modal .actions a {
        color: #333;
        padding: 8px;
        border: 1px solid #eee;
        text-decoration: none;
        margin: 10px;
    }
    .modal.sale .actions {
        color: white;
    }
    .modal.sale .actions a {
        color: white;
    }
</style>