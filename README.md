# Date-Picker-Dialog

```
    private fun showDatePickerDialog(ilDob: TextInputLayout) {

        val c = Calendar.getInstance()
        val cyear = 1990
        val month = 0
        val day = 1

        val datePickerDialog = DatePickerDialog(
            this,
            { _, year, monthOfYear, dayOfMonth ->
                var dd = dayOfMonth.toString()
                var mm = (monthOfYear + 1).toString()
                val yyyy = year.toString()
                if (dayOfMonth < 10)
                    dd = "0$dd"
                if (monthOfYear < 9)
                    mm = "0$mm"
                val date = "$mm-$dd-$yyyy"
                ilDob.editText?.setText(date)
            },
            cyear,
            month,
            day
        )
        datePickerDialog.datePicker.maxDate = c.timeInMillis
        datePickerDialog.show()
    }
```

# Time-Picker-Dialog 

```
    private fun showTimerPickerDialog(ilTime: TextInputLayout) {
        val mTimePicker = TimePickerDialog(
            this,
            { view, hourOfDay, minute ->
                var h = hourOfDay.toString()
                var m = minute.toString()
                if (hourOfDay < 10) {
                    h = "0$hourOfDay"
                }
                if (minute < 10) {
                    m = "0$minute"
                }
                ilTime.editText?.setText(
                    String.format("%s : %s", h, m)
                )
            }, 0, 0, false 
        )

        mTimePicker.show()
    }
```

# Date-Range-Picker-Dialog

```
val datePicker = MaterialDatePicker.Builder.dateRangePicker().build()
datePicker.show(supportFragmentManager, "DatePicker")
datePicker.addOnPositiveButtonClickListener {
                binding.tvDateRange.text = datePicker.headerText
  }
```

