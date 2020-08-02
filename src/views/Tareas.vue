<template>
    <div>
        <v-container>
            <v-row>    
                <v-col  md="6">
                    <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
                        <v-card-text>
                            <v-container>
                                <v-chip
                                    class="ml-0"
                                    color="pink"
                                    label
                                    text-color="white"
                                >
                                    <v-icon left>mdi-label</v-icon>
                                    {{item.titulo}}
                                </v-chip>
                                <p>{{item.descripcion}}</p>
                                <v-btn class="ml-0" color="warning" @click="editar(index)">Editar</v-btn>
                                <v-btn class="ml-5" color="error" @click="eliminarTarea(item.id)">Eliminar</v-btn>
                            </v-container>
                        </v-card-text>
                    </v-card>
                </v-col>
    
                <v-col v-if="formAgregar" md="6" class="pa-3">
                    <v-card class="mb-3 pa-3">
                        <v-form @submit.prevent="agregarTarea">
                            <v-text-field label="Titulo de la tarea" v-model="titulo"> </v-text-field>
                            <v-textarea v-model="descripcion"></v-textarea>
                            <v-btn block class="success" type="submit">Agregar Tarea</v-btn>
                        </v-form>
                    </v-card>
                </v-col>

                <v-col v-if="!formAgregar" md="6" class="pa-3">
                    <v-card class="mb-3 pa-3">
                        <v-form @submit.prevent="editarTarea">
                            <v-text-field label="Titulo de la tarea" v-model="titulo">{{}}</v-text-field>
                            <v-textarea v-model="descripcion"></v-textarea>
                            <v-btn block class="warning" type="submit">Editar tarea</v-btn>
                        </v-form>
                    </v-card>
                </v-col>
            </v-row>
            
            <v-snackbar
                v-model="snackbar"
            >
                {{ mensaje }}
                <template v-slot:action="{ attrs }">
                    <v-btn
                    color="pink"
                    text
                    v-bind="attrs"
                    @click="snackbar = false"
                    >
                    Close
                    </v-btn>
                </template>
            </v-snackbar>
        </v-container>
    </div>
</template>

<script>
export default {
    name: 'Tareas',
    data() {
        return {
            listaTareas: [
                {id:1, titulo: 'Titulo tarea #1', descripcion: 'Crixtpf, ipsum dolor sit amet consectetur adipisicing elit. Facilis amet officiis nam necessitatibus voluptatibus. Dolor facere earum qui veniam ea nam adipisci porro error temporibus, velit, illum nisi. Nobis, earum.'}
                ,{id:2, titulo: 'Titulo tarea #2', descripcion: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Facilis amet officiis nam necessitatibus voluptatibus. Dolor facere earum qui veniam ea nam adipisci porro error temporibus, velit, illum nisi. Nobis, earum.'}
                ,{id:3, titulo: 'Titulo tarea #3', descripcion: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Facilis amet officiis nam necessitatibus voluptatibus. Dolor facere earum qui veniam ea nam adipisci porro error temporibus, velit, illum nisi. Nobis, earum.'}
            ],
            titulo: '',
            descripcion: '',
            snackbar: false,
            mensaje: 'asdas',
            formAgregar: true,
            indexTarea: ''
        }
    },
    methods: {
        agregarTarea () {
            console.log(this.titulo, this.descripcion);
            if(this.titulo === '' || this.descripcion === ''){
                this.snackbar = true
                this.mensaje = 'Llenas todos los campos'
            }else {
                this.listaTareas.push({
                    id: Date.now(),
                    titulo: this.titulo,
                    descripcion: this.descripcion
                })
                this.titulo = '',
                this.descripcion = '',
                this.mensaje = 'Tarea agregada'
            }
        },
        eliminarTarea(id) {
            this.listaTareas = this.listaTareas.filter(e => e.id != id)
        },
        editar(index){
            this.formAgregar = false
            this.titulo = this.listaTareas[index].titulo
            this.descripcion = this.listaTareas[index].descripcion
            this.indexTarea = index
        },
        editarTarea(){
            this.listaTareas[this.indexTarea].titulo = this.titulo
            this.listaTareas[this.indexTarea].descripcion = this.descripcion
            this.formAgregar = true
            this.titulo = ''
            this.descripcion = ''
            this.snackbar = true
            this.mensaje = 'Editaste la tarea'
        }
    }
}
</script>