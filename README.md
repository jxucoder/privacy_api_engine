# privacy_api_engine

# Roadmap
1. mapping from entity type to privacy policy
2. detect sensitive entity key/column
3. detect sensitive entity values
4. detect sensitive entities in texts: natural language, log message, and htmls. 

# Data types
1. Tabular data

Tabular data is an arrangement of information or data, typically in rows and columns. SQL table is a form of tabular data. Given a <key: value list pair> (i.e. column: corresponding rows), we want to know if it contains any sensitive data. Most of the time, each value/row is a singular entity. They can be dates, names, addresses, etc. We can detect level of sensitivity based on key/column and also actual values. For example, we may know this table has sensitive entities if column name is "FIRST_NAME", and we may also know based on values from that column: "Kevin", "Amanda", .... We will reply on domain knowledge, common sense, and pattern matching (e.g. regex) to detect such entities. 

2. Free text

Detecting entities in free text is similar to the task of Named Entity Recognition. In this detection, we will rely more on Natural Language Processing. As free text has its own vacabulary, grammar, and various linguistic patterns. For example, the phrase after "go to" is probably a LOCATION entity, the words after "was born on" is likely birthdate. 

3. Log messages

log messages would need additional pre-processing to remove the markups.  
