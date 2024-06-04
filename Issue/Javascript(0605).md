### issue -in loop, whenever objects property has changed , the object cannnot change the new object one without new constructor  


``` javascript
tagElements.each((index, element) => {
      let tagDate = dateDatas[index].date;
      let tagHour = dateDatas[index].hour;
      
      if (_flag == 1){
        if ((tagDate == _selectedDate.today) && (tagHour >= 9 && tagHour <13)) {
          let tagTitle = $(element).text();
          let tagUrl = $(element).attr('href');
          tagData = new TagData(tagUrl, tagTitle, tagDate, tagHour);
          //console.log(tagData);
          tagDatas.push(tagData);
        } 
      } else if (_flag == 2){
        if (((tagDate == _selectedDate.today) && (tagHour < 9 )) || (((tagDate == _selectedDate.yesterday) && (tagHour >= 13 && tagHour < 22)))) {
          let tagTitle = $(element).text();
          let tagUrl = $(element).attr('href');
          tagData = new TagData(tagUrl, tagTitle, tagDate, tagHour);
          //console.log(tagData);
          tagDatas.push(tagData);  // tagData is always same object and cannot changed
        } 
      }
  });
```
