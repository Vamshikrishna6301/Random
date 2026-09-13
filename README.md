
    def department_attendance_summary(self, df: pd.DataFrame) -> pd.DataFrame:
        result = pd.crosstab(
            df["Department"],
            df["Attendance"]
        )

        result = result.reindex(
            columns=["Present", "Absent", "Leave"],
            fill_value=0
        )

        result.columns.name = None

        result = result.reset_index()

        return result
        
