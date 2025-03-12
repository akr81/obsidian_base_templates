<< [[<% tp.date.now("YYYYMMDD", -7, tp.file.title, "YYYYMMDD") %>]]  < [[<% tp.date.now("YYYYMMDD", -1, tp.file.title, "YYYYMMDD") %>]]  |  [[<% tp.date.now("YYYYMMDD", 1, tp.file.title, "YYYYMMDD") %>]]  >  [[<% tp.date.now("YYYYMMDD", 7, tp.file.title, "YYYYMMDD") %>]] >>

## メモ


## ナレッジログ

```dataview
LIST 
FROM ""
WHERE (file.mday.year = <% moment(tp.file.title, "YYYYMMDD").format("YYYY") %> and file.mday.month = <% moment(tp.file.title, "YYYYMMDD").format("MM") %> and file.mday.day = <% moment(tp.file.title, "YYYYMMDD").format("DD") %>) OR (file.cday.year = <% moment(tp.file.title, "YYYYMMDD").format("YYYY") %> and file.cday.month = <% moment(tp.file.title, "YYYYMMDD").format("MM") %> and file.cday.day = <% moment(tp.file.title, "YYYYMMDD").format("DD") %>)
SORT file.name ASC
```


---
## タスク

### 期限間近

```tasks
not done
has due date
due before <% tp.date.now("YYYY-MM-DD", 3, tp.file.title, "YYYYMMDD") %>
```

### 実施予定

```tasks
not done
scheduled before <% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYYMMDD") %>
```

### 完了

```tasks
done <% tp.date.now("YYYY-MM-DD", 0, tp.file.title, "YYYYMMDD") %>
```

