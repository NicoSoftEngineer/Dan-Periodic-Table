

<script setup>
/*<template>

    <div>
        <form @submit.prevent="generateQuestions()">
            What type of question do you want
            <select v-model="questionType">
                <option value="symb">Symbol</option>
                <option value="cz">Name in czech</option>
                <option value="en">Name in english</option>
                <option value="la">Name in latin</option>
            </select><br />
            In what are you gonna answer
            <select v-model="answerType">
                <option value="symb">Symbol</option>
                <option value="cz">Name in czech</option>
                <option value="en">Name in english</option>
                <option value="la">Name in latin</option>
            </select><br />
            How many questions do you want
            <input placeholder="write here" v-model="quantity" />
            <button>Start</button><br />
        </form>
    </div>
    <div>
        <div v-if="playing">
            {{elementsForTest}}
        </div>
        <form @submit.prevent="Check()">
            <input v-model="answer" />
            <button>Submit</button>
        </form>
    </div>



</template>*/ 






/*


import { reactive, ref } from 'vue'

const answerType = ref('cz')

const questionType = ref("symb")

const answer = ref('')
const quantity = ref(1)

const elementsForTest = reactive([
])
const max = ref(118)
//const index = ref(1)
const playing = ref(false)
const num = ref(0)

const table = reactive(
    [
        { id: 1, sign: "H", nameInEnglish: "Hydrogen", nameInCzech: "vodík", nameInLatin: "hydrogenium" },
        { id: 2, sign: "He", nameInEnglish: "Helium", nameInCzech: "helium", nameInLatin: "helium" },
        { id: 3, sign: "Li", nameInEnglish: "Lithium", nameInCzech: "lithium", nameInLatin: "lithium" },
        { id: 4, sign: "Be", nameInEnglish: "Beryllium", nameInCzech: "beryllium", nameInLatin: "beryllium" },
        { id: 5, sign: "B", nameInEnglish: "Boron", nameInCzech: "bor", nameInLatin: "borum" },
        { id: 6, sign: "C", nameInEnglish: "Carbon", nameInCzech: "uhlík", nameInLatin: "carboneum" },
        { id: 7, sign: "N", nameInEnglish: "Nitrogen", nameInCzech: "dusík", nameInLatin: "nitrogenium" },
        { id: 8, sign: "O", nameInEnglish: "Oxygen", nameInCzech: "kyslík", nameInLatin: "oxygenium" },
        { id: 9, sign: "F", nameInEnglish: "Fluorine", nameInCzech: "fluor", nameInLatin: "fluorum" },
        { id: 10, sign: "Ne", nameInEnglish: "Neon", nameInCzech: "neon", nameInLatin: "neon" },
        { id: 11, sign: "Na", nameInEnglish: "Sodium", nameInCzech: "sodík", nameInLatin: "natrium" },
        { id: 12, sign: "Mg", nameInEnglish: "Magnesium", nameInCzech: "hořčík", nameInLatin: "magnesium" },
        { id: 13, sign: "Al", nameInEnglish: "Aluminium", nameInCzech: "hliník", nameInLatin: "aluminium" },
        { id: 14, sign: "Si", nameInEnglish: "Silicon", nameInCzech: "křemík", nameInLatin: "silicium" },
        { id: 15, sign: "P", nameInEnglish: "Phosphorus", nameInCzech: "fosfor", nameInLatin: "phosphorus" },
        { id: 16, sign: "S", nameInEnglish: "Sulfur", nameInCzech: "síra", nameInLatin: "sulphur" },
        { id: 17, sign: "Cl", nameInEnglish: "Chlorine", nameInCzech: "chlor", nameInLatin: "chlorum" },
        { id: 18, sign: "Ar", nameInEnglish: "Argon", nameInCzech: "argon", nameInLatin: "argonum" },
        { id: 19, sign: "K", nameInEnglish: "Potassium", nameInCzech: "draslík", nameInLatin: "kalium" },
        { id: 20, sign: "Ca", nameInEnglish: "Calcium", nameInCzech: "vápník", nameInLatin: "calcium" },
        { id: 21, sign: "Sc", nameInEnglish: "Scandium", nameInCzech: "skandium", nameInLatin: "scandium" },
        { id: 22, sign: "Ti", nameInEnglish: "Titanium", nameInCzech: "titan", nameInLatin: "titanium" },
        { id: 23, sign: "V", nameInEnglish: "Vanadium", nameInCzech: "vanad", nameInLatin: "vanadium" },
        { id: 24, sign: "Cr", nameInEnglish: "Chromium", nameInCzech: "chrom", nameInLatin: "chromium" },
        { id: 25, sign: "Mn", nameInEnglish: "Manganese", nameInCzech: "mangan", nameInLatin: "manganum" },
        { id: 26, sign: "Fe", nameInEnglish: "Iron", nameInCzech: "železo", nameInLatin: "ferrum" },
        { id: 27, sign: "Co", nameInEnglish: "Cobalt", nameInCzech: "kobalt", nameInLatin: "cobaltum" },
        { id: 28, sign: "Ni", nameInEnglish: "Nickel", nameInCzech: "nikl", nameInLatin: "niccolum" },
        { id: 29, sign: "Cu", nameInEnglish: "Copper", nameInCzech: "měď", nameInLatin: "cuprum" },
        { id: 30, sign: "Zn", nameInEnglish: "Zinc", nameInCzech: "zinek", nameInLatin: "zincum" },
        { id: 31, sign: "Ga", nameInEnglish: "Gallium", nameInCzech: "gallium", nameInLatin: "gallium" },
        { id: 32, sign: "Ge", nameInEnglish: "Germanium", nameInCzech: "germanium", nameInLatin: "germanium" },
        { id: 33, sign: "As", nameInEnglish: "Arsenic", nameInCzech: "arsen", nameInLatin: "arsenicum" },
        { id: 34, sign: "Se", nameInEnglish: "Selenium", nameInCzech: "selen", nameInLatin: "selenium" },
        { id: 35, sign: "Br", nameInEnglish: "Bromine", nameInCzech: "brom", nameInLatin: "bromum" },
        { id: 36, sign: "Kr", nameInEnglish: "Krypton", nameInCzech: "krypton", nameInLatin: "krypton" },
        { id: 37, sign: "Rb", nameInEnglish: "Rubidium", nameInCzech: "rubidium", nameInLatin: "rubidium" },
        { id: 38, sign: "Sr", nameInEnglish: "Strontium", nameInCzech: "stroncium", nameInLatin: "strontium" },
        { id: 39, sign: "Y", nameInEnglish: "Yttrium", nameInCzech: "yttrium", nameInLatin: "yttrium" },
        { id: 40, sign: "Zr", nameInEnglish: "Zirconium", nameInCzech: "zirkonium", nameInLatin: "zirconium" },
        { id: 41, sign: "Nb", nameInEnglish: "Niobium", nameInCzech: "niob", nameInLatin: "niobium" },
        { id: 42, sign: "Mo", nameInEnglish: "Molybdenum", nameInCzech: "molybden", nameInLatin: "molybdaenum" },
        { id: 43, sign: "Tc", nameInEnglish: "Technetium", nameInCzech: "technecium", nameInLatin: "technetium" },
        { id: 44, sign: "Ru", nameInEnglish: "Ruthenium", nameInCzech: "ruthenium", nameInLatin: "ruthenium" },
        { id: 45, sign: "Rh", nameInEnglish: "Rhodium", nameInCzech: "rhodium", nameInLatin: "rhodium" },
        { id: 46, sign: "Pd", nameInEnglish: "Palladium", nameInCzech: "palladium", nameInLatin: "palladium" },
        { id: 47, sign: "Ag", nameInEnglish: "Silver", nameInCzech: "stříbro", nameInLatin: "argentum" },
        { id: 48, sign: "Cd", nameInEnglish: "Cadmium", nameInCzech: "kadmium", nameInLatin: "cadmium" },
        { id: 49, sign: "In", nameInEnglish: "Indium", nameInCzech: "indium", nameInLatin: "indium" },
        { id: 50, sign: "Sn", nameInEnglish: "Tin", nameInCzech: "cín", nameInLatin: "stannum" },
        { id: 51, sign: "Sb", nameInEnglish: "Antimony", nameInCzech: "antimon", nameInLatin: "stibium" },
        { id: 52, sign: "Te", nameInEnglish: "Tellurium", nameInCzech: "tellur", nameInLatin: "tellurium" },
        { id: 53, sign: "I", nameInEnglish: "Iodine", nameInCzech: "jod", nameInLatin: "iodum" },
        { id: 54, sign: "Xe", nameInEnglish: "Xenon", nameInCzech: "xenon", nameInLatin: "xenon" },
        { id: 55, sign: "Cs", nameInEnglish: "Caesium", nameInCzech: "cesium", nameInLatin: "caesium" },
        { id: 56, sign: "Ba", nameInEnglish: "Barium", nameInCzech: "baryum", nameInLatin: "barium" },
        { id: 57, sign: "La", nameInEnglish: "Lanthanum", nameInCzech: "lanthan", nameInLatin: "lanthanum" },
        { id: 58, sign: "Ce", nameInEnglish: "Cerium", nameInCzech: "cer", nameInLatin: "cerium" },
        { id: 59, sign: "Pr", nameInEnglish: "Praseodymium", nameInCzech: "praseodym", nameInLatin: "praseodymium" },
        { id: 60, sign: "Nd", nameInEnglish: "Neodymium", nameInCzech: "neodym", nameInLatin: "neodymium" },
        { id: 61, sign: "Pm", nameInEnglish: "Promethium", nameInCzech: "promethium", nameInLatin: "promethium" },
        { id: 62, sign: "Sm", nameInEnglish: "Samarium", nameInCzech: "samarium", nameInLatin: "samarium" },
        { id: 63, sign: "Eu", nameInEnglish: "Europium", nameInCzech: "europium", nameInLatin: "europium" },
        { id: 64, sign: "Gd", nameInEnglish: "Gadolinium", nameInCzech: "gadolinium", nameInLatin: "gadolinium" },
        { id: 65, sign: "Tb", nameInEnglish: "Terbium", nameInCzech: "terbium", nameInLatin: "terbium" },
        { id: 66, sign: "Dy", nameInEnglish: "Dysprosium", nameInCzech: "dysprosium", nameInLatin: "dysprosium" },
        { id: 67, sign: "Ho", nameInEnglish: "Holmium", nameInCzech: "holmium", nameInLatin: "holmium" },
        { id: 68, sign: "Er", nameInEnglish: "Erbium", nameInCzech: "erbium", nameInLatin: "erbium" },
        { id: 69, sign: "Tm", nameInEnglish: "Thulium", nameInCzech: "thulium", nameInLatin: "thulium" },
        { id: 70, sign: "Yb", nameInEnglish: "Ytterbium", nameInCzech: "ytterbium", nameInLatin: "ytterbium" },
        { id: 71, sign: "Lu", nameInEnglish: "Lutetium", nameInCzech: "lutecium", nameInLatin: "lutetium" },
        { id: 72, sign: "Hf", nameInEnglish: "Hafnium", nameInCzech: "hafnium", nameInLatin: "hafnium" },
        { id: 73, sign: "Ta", nameInEnglish: "Tantalum", nameInCzech: "tantal", nameInLatin: "tantalum" },
        { id: 74, sign: "W", nameInEnglish: "Tungsten", nameInCzech: "wolfram", nameInLatin: "wolframium" },
        { id: 75, sign: "Re", nameInEnglish: "Rhenium", nameInCzech: "rhenium", nameInLatin: "rhenium" },
        { id: 76, sign: "Os", nameInEnglish: "Osmium", nameInCzech: "osmium", nameInLatin: "osmium" },
        { id: 77, sign: "Ir", nameInEnglish: "Iridium", nameInCzech: "iridium", nameInLatin: "iridium" },
        { id: 78, sign: "Pt", nameInEnglish: "Platinum", nameInCzech: "platina", nameInLatin: "platinum" },
        { id: 79, sign: "Au", nameInEnglish: "Gold", nameInCzech: "zlato", nameInLatin: "aurum" },
        { id: 80, sign: "Hg", nameInEnglish: "Mercury", nameInCzech: "rtuť", nameInLatin: "hydrargyrum" },
        { id: 81, sign: "Tl", nameInEnglish: "Thallium", nameInCzech: "thallium", nameInLatin: "thallium" },
        { id: 82, sign: "Pb", nameInEnglish: "Lead", nameInCzech: "olovo", nameInLatin: "plumbum" },
        { id: 83, sign: "Bi", nameInEnglish: "Bismuth", nameInCzech: "bismut", nameInLatin: "bismuthum" },
        { id: 84, sign: "Po", nameInEnglish: "Polonium", nameInCzech: "polonium", nameInLatin: "polonium" },
        { id: 85, sign: "At", nameInEnglish: "Astatine", nameInCzech: "astat", nameInLatin: "astatium" },
        { id: 86, sign: "Rn", nameInEnglish: "Radon", nameInCzech: "radon", nameInLatin: "radon" },
        { id: 87, sign: "Fr", nameInEnglish: "Francium", nameInCzech: "francium", nameInLatin: "francium" },
        { id: 88, sign: "Ra", nameInEnglish: "Radium", nameInCzech: "radium", nameInLatin: "radium" },
        { id: 89, sign: "Ac", nameInEnglish: "Actinium", nameInCzech: "aktinium", nameInLatin: "actinium" },
        { id: 90, sign: "Th", nameInEnglish: "Thorium", nameInCzech: "thorium", nameInLatin: "thorium" },
        { id: 91, sign: "Pa", nameInEnglish: "Protactinium", nameInCzech: "protaktinium", nameInLatin: "protactinium" },
        { id: 92, sign: "U", nameInEnglish: "Uranium", nameInCzech: "uran", nameInLatin: "uranium" },
        { id: 93, sign: "Np", nameInEnglish: "Neptunium", nameInCzech: "neptunium", nameInLatin: "neptunium" },
        { id: 94, sign: "Pu", nameInEnglish: "Plutonium", nameInCzech: "plutonium", nameInLatin: "plutonium" },
        { id: 95, sign: "Am", nameInEnglish: "Americium", nameInCzech: "americium", nameInLatin: "americium" },
        { id: 96, sign: "Cm", nameInEnglish: "Curium", nameInCzech: "curium", nameInLatin: "curium" },
        { id: 97, sign: "Bk", nameInEnglish: "Berkelium", nameInCzech: "berkelium", nameInLatin: "berkelium" },
        { id: 98, sign: "Cf", nameInEnglish: "Californium", nameInCzech: "kalifornium", nameInLatin: "californium" },
        { id: 99, sign: "Es", nameInEnglish: "Einsteinium", nameInCzech: "einsteinium", nameInLatin: "einsteinium" },
        { id: 100, sign: "Fm", nameInEnglish: "Fermium", nameInCzech: "fermium", nameInLatin: "fermium" },
        { id: 101, sign: "Md", nameInEnglish: "Mendelevium", nameInCzech: "mendelevium", nameInLatin: "mendelevium" },
        { id: 102, sign: "No", nameInEnglish: "Nobelium", nameInCzech: "nobelium", nameInLatin: "nobelium" },
        { id: 103, sign: "Lr", nameInEnglish: "Lawrencium", nameInCzech: "lawrencium", nameInLatin: "lawrencium" },
        { id: 104, sign: "Rf", nameInEnglish: "Rutherfordium", nameInCzech: "rutherfordium", nameInLatin: "rutherfordium" },
        { id: 105, sign: "Db", nameInEnglish: "Dubnium", nameInCzech: "dubnium", nameInLatin: "dubnium" },
        { id: 106, sign: "Sg", nameInEnglish: "Seaborgium", nameInCzech: "seaborgium", nameInLatin: "seaborgium" },
        { id: 107, sign: "Bh", nameInEnglish: "Bohrium", nameInCzech: "bohrium", nameInLatin: "bohrium" },
        { id: 108, sign: "Hs", nameInEnglish: "Hassium", nameInCzech: "hassium", nameInLatin: "hassium" },
        { id: 109, sign: "Mt", nameInEnglish: "Meitnerium", nameInCzech: "meitnerium", nameInLatin: "meitnerium" },
        { id: 110, sign: "Ds", nameInEnglish: "Darmstadtium", nameInCzech: "darmstadtium", nameInLatin: "darmstadtium" },
        { id: 111, sign: "Rg", nameInEnglish: "Roentgenium", nameInCzech: "roentgenium", nameInLatin: "roentgenium" },
        { id: 112, sign: "Cn", nameInEnglish: "Copernicium", nameInCzech: "kopernicium", nameInLatin: "copernicium" },
        { id: 113, sign: "Nh", nameInEnglish: "Nihonium", nameInCzech: "nihonium", nameInLatin: "nihonium" },
        { id: 114, sign: "Fl", nameInEnglish: "Flerovium", nameInCzech: "flerovium", nameInLatin: "flerovium" },
        { id: 115, sign: "Mc", nameInEnglish: "Moscovium", nameInCzech: "moscovium", nameInLatin: "moscovium" },
        { id: 116, sign: "Lv", nameInEnglish: "Livermorium", nameInCzech: "livermorium", nameInLatin: "livermorium" },
        { id: 117, sign: "Ts", nameInEnglish: "Tennessine", nameInCzech: "tennessin", nameInLatin: "tennessine" },
        { id: 118, sign: "Og", nameInEnglish: "Oganesson", nameInCzech: "oganesson", nameInLatin: "oganesson" },

    ]
)

/*function generateQuestions() {
    if (answerType.value == questionType.value) {
        alert('You cannot have the same type of question as the type of answer, please try again')
    }
    else {
        playing.value = !playing.value
        console.log('called')
        for (let i = 0; i <= quantity.value; i++) {
            num.value = Math.floor((Math.random() * max.value) + 1)
            elementsForTest.value.push(table.filter(x => x.id == num.value).value[0])

        }
        console.log(elementsForTest.length + "věcí")
    }
}


function Check() {
    if (answerType.value == 'symb') {
        if (questionType.value == 'cz') {
            const score = computed(() => {

            })
        }
        else if (questionType.value == 'en') {

        }
        else if (questionType.value == 'la') {

        }
    }
    /*else if (answerType.value == 'cz') {
        if (questionType.value == 'sym') {

        }
        else if (questionType.value == 'en') {

        }
        else if (questionType.value == 'la') {

        }
    }
    else if (answerType.value == 'en') {
        if (questionType.value == 'sym') {

        }
        else if (questionType.value == 'cz') {

        }
        else if (questionType.value == 'la') {

        }
    }
    else if (answerType.value == 'la') {
        if (questionType.value == 'sym') {

        }
        else if (questionType.value == 'cz') {

        }
        else if (questionType.value == 'en') {

        }
    }


}
*/
</script>