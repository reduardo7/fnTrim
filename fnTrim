-- =============================================
-- Author:		Eduardo Daniel Cuomo
-- Create date: 29/05/2015
-- Description:	Complete Trim
-- =============================================
CREATE FUNCTION [dbo].[fnTrim] (
	@Str NVARCHAR(MAX)
) RETURNS NVARCHAR(MAX) AS BEGIN
	DECLARE @StrPrv NVARCHAR(MAX) = N''
	
	WHILE ((@StrPrv <> @Str) AND (@Str IS NOT NULL)) BEGIN
		SET @StrPrv = @Str
		
		-- Beginning
		IF EXISTS (SELECT 1 WHERE @Str LIKE '[' + CHAR(13) + CHAR(10) + CHAR(9) + ']%')
			SET @Str = LTRIM(RIGHT(@Str, LEN(@Str) - 1))
		
		-- Ending
		IF EXISTS (SELECT 1 WHERE @Str LIKE '%[' + CHAR(13) + CHAR(10) + CHAR(9) + ']')
			SET @Str = RTRIM(LEFT(@Str, LEN(@Str) - 1))
	END

	RETURN @StrPrv
END
