关于SQL 性能的文章：
https://blog.csdn.net/dba_huangzj/article/details/53171963



SQL Query slow in _NET application but instantaneous in SQL Server Management Studio - Stack Overflow

https://stackoverflow.com/questions/2736638/sql-query-slow-in-net-application-but-instantaneous-in-sql-server-management-st

using (SqlConnection conn = new SqlConnection("<CONNECTION_STRING>")) {
    conn.Open();

    using (SqlCommand comm = new SqlCommand("SET ARITHABORT ON", conn)) {
        comm.ExecuteNonQuery();
    }

    // Do your own stuff here but you must use the same connection object
    // The SET command applies to the connection. Any other connections will not
    // be affected, nor will any new connections opened. If you want this applied
    // to every connection, you must do it every time one is opened.
}
