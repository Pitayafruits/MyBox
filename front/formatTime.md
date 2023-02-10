```vue
<el-table-column
  prop="complaintTime"
  :formatter="formatTime"
  label="时间"\>
</el-table-column>
```

```vue
//格式化时间
formatTime(row, column) {
   let data = row[column.property];
   let dtime = new Date(data);
   const year = dtime.getFullYear();
   let month = dtime.getMonth() + 1;
   if (month < 10) {
     month = "0" + month;
   }
   let day = dtime.getDate();
   if (day < 10) {
     day = "0" + day;
   }
   let hour = dtime.getHours();
   if (hour < 10) {    
     hour = "0" + hour;
   }
   let minute = dtime.getMinutes();
   if (minute < 10) {
     minute = "0" + minute;
   }
   let second = dtime.getSeconds();
   if (second < 10) {
     second = "0" + second;
   }
   return (    
     year + "-" + month + "-" + day + " " + hour + ":" + minute + ":" + second);
  },
```

 使用 :formatter属性，并在method中加上时间格式化方法