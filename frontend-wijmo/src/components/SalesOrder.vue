<template>
    <div>
        <div>
            <div class="label-title">수주 번호</div>
            <String label="입력하세요." v-model="value.salesOrderNumber" :editMode="editMode"/>
            <div class="label-title">수주 담당자</div>
            <String label="입력하세요." v-model="value.salesPerson" :editMode="editMode"/>
        </div>

        <div>
            <CompanyId offline label="CompanyId" v-model="value.companyId" :editMode="editMode" @change="change"/>
            <SalesType offline label="SalesType" v-model="value.salesType" :editMode="editMode" @change="change"/>
        </div>

        <div>
            <SalesItemManager offline label="SalesItems" v-model="value.salesItems" :editMode="editMode" @change="change"/>
        </div>

        <v-divider class="border-opacity-100 my-divider"></v-divider>
        <v-layout row justify-end>
            <v-btn
                width="64px"
                color="primary"
                @click="save"
            >
                저장
            </v-btn>
        </v-layout>

        <v-snackbar
            v-model="snackbar.status"
            :top="true"
            :timeout="snackbar.timeout"
            color="error"
        >
            {{ snackbar.text }}
            <v-btn dark text @click="snackbar.status = false">
                Close
            </v-btn>
        </v-snackbar>
    </div>
</template>


<script>
import BaseEntity from './base-ui/BaseEntity'

export default {
    name: 'Company',
    mixins:[BaseEntity],
    components:{
    },
    
    data: () => ({
        path: "salesOrders"
    }),
    created(){
    },
    computed:{
    },
    methods: {
    },
}
</script>

