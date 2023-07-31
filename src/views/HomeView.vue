<template>
    <div class="col-12">
        API VERSION: {{ contests.api_version }}
        <li v-for="item in contests.data.objects">
            {{ item.name }}
        </li>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    data: () => ({
        contests: [],
        currentPage: 1
    }),
    methods: {
        async getContests() {
            const contestAPI =
                'https://cors-anywhere.herokuapp.com/https://oj.vnoi.info/api/v2/contests'
            try {
                const res = await axios.get(contestAPI)
                this.contests = res.data
            } catch (e) {
                console.log(e)
            }
        }
    },
    created() {
        this.getContests()
    }
}
</script>
