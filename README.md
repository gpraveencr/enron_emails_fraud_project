# Udacity DAND Project Overview
This project is based on Udacity Data Analyst Nano Degree program.

# Understanding the Dataset and Question:

    total number of data points - 146 rows × 21 columns
    allocation across classes (POI/non-POI)
      POI - 18
    number of features - 20
    are there features with many missing values? etc.
      Missing values per column:
      bonus                         64
      deferral_payments            107
      deferred_income               97
      director_fees                129
      exercised_stock_options       44
      expenses                      51
      from_messages                 60
      from_poi_to_this_person       60
      from_this_person_to_poi       60
      loan_advances                142
      long_term_incentive           80
      other                         53
      poi                            0
      restricted_stock              36
      restricted_stock_deferred    128
      salary                        51
      shared_receipt_with_poi       60
      to_messages                   60
      total_payments                21
      total_stock_value             20

#Outlier Investigation (Below listed values are outside 4 standard deviation):
          salary outliers:  1
          bonus outliers:  3
          total_payments outliers:  2
          deferral_payments outliers:  3
          deferred_income outliers:  3
          director_fees outliers:  0
          exercised_stock_options outliers:  2
          expenses outliers:  2
          from_messages outliers:  2
          from_poi_to_this_person outliers:  1
          from_this_person_to_poi outliers:  2
          long_term_incentive outliers:  1
          shared_receipt_with_poi outliers:  1
          to_messages outliers:  2
          total_stock_value outliers:  1

  #Optimize Feature Selection/Engineering:
    Create new features:
          Created a new feature called 'poi_val'. This new column will have 'int' value of 'poi'
              df['poi_val'] = (df['poi']).astype(int)
    
    Using SelectKBest below are scores for each of the features
![SelectKBest](https://raw.githubusercontent.com/gpraveencr/enron_emails_fraud_project/master/images/selectkbest.png)

    #Properly scale features
      #below listed features were scaled
        cols_to_norm = ['bonus'                        ,
                  'deferral_payments'            ,
                  'deferred_income'              ,
                  'director_fees'                ,
                  'exercised_stock_options'      ,
                  'expenses'                     ,
                  'from_messages'                ,
                  'from_poi_to_this_person'      ,
                  'from_this_person_to_poi'      ,
                  'loan_advances'                ,
                  'long_term_incentive'          ,
                  'other'                        ,
                  'poi'                          ,
                  'restricted_stock'             ,
                  'restricted_stock_deferred'    ,
                  'salary'                       ,
                  'shared_receipt_with_poi'      ,
                  'to_messages'                  ,
                  'total_payments'               ,
                  'total_stock_value']

These are my results:
![Results](https://raw.githubusercontent.com/gpraveencr/enron_emails_fraud_project/master/images/results.png)
