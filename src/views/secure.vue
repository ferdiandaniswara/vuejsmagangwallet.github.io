<template>
    <div id="secure">
        
            <div class="container">
            <h2>History</h2>
            <b-table hover :items="items"></b-table>
            </div>
    </div>
</template>
            
        
        
    


<script>
    export default {
         name: '',
        data() {
            return {
        items: [
          { Tanggal: "2020-31-01", Tipe: "CREDIT", Nominal: 100000, Keterangan :"-"},
          { Tanggal: "2020-31-01", Tipe: "DEBIT", Nominal: 100000, Keterangan: "Beli Pulsa" },
    
        ]
      }
    }
  }
</script>

<style scoped>
    h2 {
        font-style: italic;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        
    }
    .container {
        width: 800px;
        border: 25px solid rgb(46, 172, 184);
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 100px;
        border-radius: 30px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        padding: 20px;
        box-shadow: 40px 40px 45px rgba(0, 0, 0, 0.3);
        
    }
</style>
