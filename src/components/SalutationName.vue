<template>
    <div>
      <select 
            name="salutation" 
            @change="updateSalutation"
        >
        <option value="">-</option>
        <option
          v-for="item of salutations"
          :value="item"
          :key="item"
          :selected="salutation === item"
        >
          {{ item }}
        </option>
      </select>
  
      <input
        :value="name"
        @input="updateName"
        type="text"
        name="name"
      />
    </div>
</template>

<script>
const salutations = [
    'Ms.',
    'Mrs.',
    'Miss',
    'Mx.',
    'Dr.'
]

export default {
    props: {
        salutation: {
            type: String,
            default: ''
        },
        salutationModifiers: {
            default: () => ({}),
            type: Object
        },
        name: {
            type: String,
            default: ''
        },
        nameModifiers: {
            default: () => ({}),
            type: Object
        }
    },
    setup (props, { emit }) {
        const updateSalutation = event => {
            let val = event.target.value
            if (props.salutationModifiers.capitalize) {
                val = val.toUpperCase()
            }
            emit('update:salutation', val)
        }

        const updateName = event => {
            let val = event.target.value
            if (props.nameModifiers.capitalize) {
                val = val.charAt(0).toUpperCase() + val.slice(1)
            }
            emit('update:name', val)
        }
        return {
            salutations,
            updateSalutation,
            updateName,
        }
    }
}
</script>