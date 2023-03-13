<script lang="ts">
import formInput from './components/formInput.vue'
import currencySelect from './components/currencySelect.vue'
import myButton from './components/myButton.vue'
import { defineComponent } from 'vue'

export default defineComponent({
  components: {
    formInput,
    currencySelect,
    myButton
  },
  data() {
    return {
      form: {
        owner: '',
        description: '',
        groupPolicyNumber: null,
        estNumberOfEmployees: null,
        billing: null,
        name: '',
        email: '',
        address: '',
        phone: '',
        plan: '',
        coverage: '',
        deductible: null,
        medicalBenefit: '',
        medicalBenefitAmount: null,
        currency: '',
        medicalBenefitAmountCurrency: '',
        visionBenefit: '',
        visionBenefitAmount: null,
        dentalBenefit: '',
        dentalBenefitAmount: null,
        genericPrescriptions: '',
        genericPrescriptionsAmount: null,
        nonGenericPrescriptions: '',
        nonGenericPrescriptionsAmount: null
      }
    }
  },

  methods: {
    save() {
      console.log(this.form)
    }
  }
})
</script>
<template>
  <div class="w-full h-auto bg-gray-200 flex justify-center items-center p-[10px]">
    <form
      @submit.prevent="save"
      class="relative w-[995px] h-[1470px] bg-white flex flex-col justify-evenly items-center p-[24px] rounded-lg shadow-md"
    >
      <!-- Page Header -->
      <section class="w-[100%] flex justify-between items-center mb-[16px]">
        <header class="flex items-center min-w-[350px] h-[100%]">
          <button
            class="flex items-center justify-center mr-[16px] pr-3 h-[16px] border-r-[1px] border-[#C2C7D6]"
          >
            <img class="h-[12px] w-[16px]" src="./assets/arrowback.svg" alt="arrowback" />
          </button>

          <h1 class="font-[700] text-[24px] text-[#080056]">Set Up a Self-Funded Account</h1>
        </header>
        <button><img class="w-[20px] h-[20px]" src="./assets/cancel.svg" alt="cancel" /></button>
      </section>

      <main
        class="h-[1318px] flex flex-col items-center border-[#C2C7D6] border-[0.5px] rounded-lg w-[100%] pt-[12px] p-[12px] pb-[24px]"
      >
        <!--Account Owner  -->

        <section class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto mb-[24px]">
          <label class="flex flex-col">
            <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Owner</span>
            <formInput
              name="owner"
              v-model="form.owner"
              type="text"
              placeholder="Autoloaded"
              class="bg-[#F6F7F9] border-[#F0F4FE]"
            />
          </label>

          <label class="flex flex-col">
            <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Group Policy number</span>
            <formInput
              name="goupPolicyNumber"
              v-model="form.groupPolicyNumber"
              type="text"
              placeholder="MTN - NG - CORPBILLACT- 0001"
              class="bg-[#F6F7F9] border-[#F0F4FE]"
            />
          </label>
          <label class="flex flex-col">
            <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]"
              >Description
              <span class="text-[12px] font-normal text-[#667499]">(optional)</span></span
            >
            <formInput
              name="description"
              v-model="form.description"
              type="text"
              placeholder="Enter"
            />
          </label>

          <label class="flex flex-col">
            <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]"
              >Est.number of employees</span
            >
            <formInput
              name="estNumberOfEmployees"
              v-model="form.estNumberOfEmployees"
              type="number"
              placeholder="Enter"
              class=""
            />
          </label>
        </section>

        <!-- Billing Preference -->

        <section class="w-[100%] h-[80px]">
          <header class="mb-[12px]">
            <h3 class="font-[600] text-[14px] text-[#14171F]">Billing Preference</h3>
          </header>
          <div class="flex">
            <input
              type="radio"
              name="billing"
              value="daily"
              v-model="form.billing"
              class="mr-[8px] accent-[#FE4D3C] w-[24px] h-[24px]"
              id="daily"
            />
            <label for="daily" class="mr-[28px] text-[#14171F] text-[14px] font-[400]">
              Daily</label
            >
            <input
              type="radio"
              name="billing"
              value="weekly"
              v-model="form.billing"
              class="mr-[8px] accent-[#FE4D3C] w-[24px] h-[24px]"
              id="weekly"
            />
            <label for="weekly" class="mr-[28px] text-[#14171F] text-[14px] font-[400]">
              Weekly</label
            >
            <input
              type="radio"
              name="billing"
              id="bi-weekly"
              value="bi-weekly"
              v-model="form.billing"
              class="mr-[8px] accent-[#FE4D3C] w-[24px] h-[24px]"
            />
            <label for="bi-weekly" class="mr-[28px] text-[#14171F] text-[14px] font-[400]">
              Bi-weekly</label
            >
            <input
              type="radio"
              name="billing"
              value="monthly"
              v-model="form.billing"
              class="mr-[8px] accent-[#FE4D3C] w-[24px] h-[24px]"
              id="monthly"
            />
            <label for="monthly" class="mr-[28px] text-[#14171F] text-[14px] font-[400]">
              Monthly</label
            >
          </div>
        </section>

        <!-- Billing contact -->
        <section>
          <header>
            <h3 class="font-[400] text-[16px] text-[#114FF5]">Billing Contact</h3>
          </header>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-[380px] py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Name</span>
              <formInput name="name" v-model="form.name" type="text" placeholder="Enter" />
            </label>

            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Address </span>
              <formInput name="address" v-model="form.address" type="text" placeholder="Enter" />
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Email</span>
              <formInput name="email" v-model="form.email" type="email" placeholder="Enter" />
            </label>

            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Phone</span>
              <formInput name="phone" v-model="form.phone" type="phone" placeholder="Enter" />
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Plan</span>
              <formInput name="plan" v-model="form.plan" type="text" placeholder="Enter" />
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Coverage</span>
              <formInput name="coverage" v-model="form.coverage" type="text" placeholder="Enter" />
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Deductible</span>
              <div class="flex">
                <formInput
                  name="deductible"
                  v-model="form.deductible"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect />
              </div>
            </label>
          </div>
        </section>

        <!-- Medical Benefits -->
        <section>
          <header>
            <h3 class="font-[400] text-[16px] text-[#114FF5]">Medical Benefits</h3>
          </header>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Medical Benefits</span>
              <div class="flex">
                <select
                  class="w-[469.5px] h-[40px] text-[14px] border rounded-lg text-[#667499] border-[#C2C7D6] py-2 px-6"
                  v-model="form.medicalBenefit"
                >
                  <option disabled value="">Select</option>
                  <option>benefit 1</option>
                  <option>benefit 2</option>
                  <option>benefit 3</option>
                </select>
              </div>
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Amount</span>
              <div class="flex">
                <formInput
                  name="medicalBenefitAmount"
                  v-model="form.medicalBenefitAmount"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect v-model="form.currency" />
              </div>
            </label>
          </div>
        </section>

        <!-- Vision Benefits -->
        <section class="mb-[52px]">
          <header>
            <h3 class="font-[400] text-[16px] text-[#114FF5]">Vision Benefits</h3>
          </header>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Vision Benefits</span>
              <div class="flex">
                <select
                  class="w-[469.5px] h-[40px] text-[14px] border rounded-lg text-[#667499] border-[#C2C7D6] py-2 px-6"
                  v-model="form.visionBenefit"
                >
                  <option value="">Select</option>
                  <option>benefit 1</option>
                  <option>benefit 2</option>
                  <option>benefit 3</option>
                </select>
              </div>
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Amount</span>
              <div class="flex">
                <formInput
                  name="amount"
                  v-model="form.visionBenefitAmount"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect />
              </div>
            </label>
          </div>
        </section>

        <!-- Dental Benefits -->
        <section class="mb-[24px]">
          <header>
            <h3 class="font-[400] text-[16px] text-[#114FF5]">Dental Benefits</h3>
          </header>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Dental Benefits</span>
              <div class="flex">
                <select
                  class="w-[469.5px] h-[40px] text-[14px] border rounded-lg text-[#667499] border-[#C2C7D6] py-2 px-6"
                  v-model="form.dentalBenefit"
                >
                  <option value="">Select</option>
                  <option>benefit 1</option>
                  <option>benefit 2</option>
                  <option>benefit 3</option>
                </select>
              </div>
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Amount</span>
              <div class="flex">
                <formInput
                  name="amount"
                  v-model="form.dentalBenefitAmount"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect />
              </div>
            </label>
          </div>
        </section>

        <!-- Pharmacy Benefits -->
        <section>
          <header>
            <h3 class="font-[400] text-[16px] text-[#114FF5]">Pharmacy Benefits</h3>
          </header>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]"
                >Generics Prescriptions</span
              >
              <div class="flex">
                <select
                  class="w-[469.5px] h-[40px] text-[14px] border rounded-lg text-[#667499] border-[#C2C7D6] py-2 px-6"
                  v-model="form.genericPrescriptions"
                >
                  <option value="">Select</option>
                  <option>prescription 1</option>
                  <option>prescription 2</option>
                  <option>prescription 3</option>
                </select>
              </div>
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Amount</span>
              <div class="flex">
                <formInput
                  name="amount"
                  v-model="form.genericPrescriptionsAmount"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect />
              </div>
            </label>
          </div>
          <div class="grid grid-cols-2 gap-6 content-center w-[100%] h-auto py-[12px]">
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]"
                >Non-Generics (Specialty Brand Drugs) Prescriptions</span
              >
              <div class="flex">
                <select
                  class="w-[469.5px] h-[40px] text-[14px] border rounded-lg text-[#667499] border-[#C2C7D6] py-2 px-6"
                  v-model="form.nonGenericPrescriptions"
                >
                  <option value="">Select</option>
                  <option>prescription 1</option>
                  <option>prescription 2</option>
                  <option>prescription 3</option>
                </select>
              </div>
            </label>
            <label class="flex flex-col">
              <span class="font-[600] text-[14px] text-[#14171F] mb-[4px]">Amount</span>
              <div class="flex">
                <formInput
                  name="amount"
                  v-model="form.nonGenericPrescriptionsAmount"
                  type="number"
                  placeholder="0"
                  class="w-[357.5px] mr-[4px] rounded-[4px]"
                />
                <currencySelect />
              </div>
            </label>
          </div>
        </section>
      </main>

      <!-- CTAs -->
      <section class="w-[100%] flex justify-end mt-[26px]">
        <myButton>Save as Draft</myButton>
        <myButton
          type="submit"
          :disabled="
            !form.owner ||
            !form.address ||
            !form.billing ||
            !form.coverage ||
            !form.deductible ||
            !form.dentalBenefit ||
            !form.dentalBenefitAmount ||
            !form.email ||
            !form.estNumberOfEmployees ||
            !form.genericPrescriptions ||
            !form.genericPrescriptionsAmount ||
            !form.groupPolicyNumber ||
            !form.phone ||
            !form.medicalBenefit ||
            !form.medicalBenefitAmount ||
            !form.name ||
            !form.plan ||
            !form.visionBenefit ||
            !form.visionBenefitAmount ||
            !form.nonGenericPrescriptionsAmount ||
            !form.nonGenericPrescriptions
          "
          :class="{
            'bg-[#FE4D3C]/50 cursor-not-allowed':
              !form.owner ||
              !form.address ||
              !form.billing ||
              !form.coverage ||
              !form.deductible ||
              !form.dentalBenefit ||
              !form.dentalBenefitAmount ||
              !form.email ||
              !form.estNumberOfEmployees ||
              !form.genericPrescriptions ||
              !form.genericPrescriptionsAmount ||
              !form.groupPolicyNumber ||
              !form.phone ||
              !form.medicalBenefit ||
              !form.medicalBenefitAmount ||
              !form.name ||
              !form.plan ||
              !form.visionBenefit ||
              !form.visionBenefitAmount ||
              !form.nonGenericPrescriptions ||
              !form.nonGenericPrescriptionsAmount
          }"
          class="bg-[#FE4D3C] text-white border-none ml-[16px]"
          >Save</myButton
        >
      </section>
    </form>
  </div>
</template>

<style>
html,
body {
  font-family: 'Inter', sans-serif;
}
</style>
