<template>
    <h2 class="title">Reminder</h2>
    <section class="container">
        <h2 class="sub-title">Pinned</h2>
        <div v-for="item in reminders">
            <div v-if="item.isPinned" class="reminder">
                <h3>{{ item.content.title }}</h3>
                <p>{{ item.content.text }}</p>
                <p>{{ item.time }}</p>
            </div>
        </div>
        <h2 class="sub-title">Upcoming</h2>
        <div v-for="item in reminders">
            <div v-if="!item.isPinned" class="reminder">
                <h3>{{ item.content.title }}</h3>
                <p>{{ item.content.text }}</p>
                <p>{{ item.time }}</p>
            </div>
        </div>
    </section>
</template>
<script>

export default {
    data() {
        return {
            reminders: [{
                time: new Date(2024, 6, 1, 15, 0, 0, 0).getFullYear(),
                content: {
                    title: 'Coffee',
                    text: 'Have a coffee with a friends',
                },
                isPinned: true,
            },
            {
                time: new Date(2024, 6, 1, 15, 0, 0, 0),
                content: {
                    title: 'Cake',
                    text: 'Have a coffee with a friends',
                },
                isPinned: false,
            },
            ]
        }
    }
}

</script>
<style scoped>
.title {
    text-align: center;
    font-size: clamp(2rem, 8vw, 3rem);
}

.sub-title {
    margin: 0.8rem 0;
}

.container {
    display: flex;
    flex-direction: column;
    align-items: left;
    max-width: 50em;
    width: 100%;
    background-color: rgb(255, 194, 245);
    padding: 1rem;
    margin-top: 2rem;
    border-radius: 1rem;
}

.reminder {
    display: flex;
    flex-direction: column;
    min-height: 6em;
    font-weight: 600;
    gap: 0.3rem;
    background-color: rgb(211, 164, 255);
    border-radius: 1rem;
    padding: 1rem;
}
</style>