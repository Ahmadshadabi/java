# java
Name:game Little

private void birdBox_Click(object sender, EventArgs e)
		{	if (GameStatus == GameStatus.Continue)		{
				BirdBox birdbox = (BirdBox)sender;

			if (birdbox != null && birdbox.Status != "Dead")
			{
					PlayBirdHitSound();
					birdbox.Status = "Dead";
				birdbox.Image.RotateFlip(RotateFlipType.Rotate270FlipNone);
					birdbox.Image = Properties.Resources.explosion_animation;
				}
				else
				{
					PlayGunSound();
				}
			}
		}
		
		private void PlayGameForm_Click(object sender, EventArgs e)
		{
			if (GameStatus == GameStatus.Continue)
			{
				PlayGunSound();
			}
		}		

		private void RemoveBird(BirdTimer BirdTimer)	{
			if (BirdTimer != null)
			{
				FlyingBirds.Remove(BirdTimer);

				BirdTimer.Stop();
				BirdTimer.BirdBox.Dispose();
				BirdTimer.Dispose();
			}
		}
 

